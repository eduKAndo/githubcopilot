# Exercício: Usando o GitHub Copilot para conectar ao (new) Outlook

## Objetivo
Neste exercício, você aprenderá a **utilizar o GitHub Copilot** e o **GitHub Copilot Chat** para gerar um projeto **console** no **Visual Studio Code** que se conecte à caixa de entrada do **Outlook**, obtendo **assunto e data dos últimos X e-mails recebidos e enviados**. Em seguida, ajustaremos o código para incluir a **data da resposta do usuário**, caso exista.

## Passo a Passo

### 1. Configurando o Ambiente

Antes de começar, certifique-se de que possui:
- **Visual Studio Code** instalado ([Download](https://code.visualstudio.com/))
- **Extensão do C#** instalada no VS Code
- **GitHub Copilot e Copilot Chat** instalados e autenticados ([Guia de Instalação](https://github.com/features/copilot))
- **.NET SDK** instalado ([Download](https://dotnet.microsoft.com/en-us/download))
- **Conta do Outlook** configurada com acesso IMAP/SMTP ou API do Microsoft Graph

Se ainda não instalou o **GitHub Copilot**, siga o [passo a passo de instalação](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot).

### 2. Criando o Projeto Console no VS Code

1. **Abra o VS Code**.
2. **No terminal integrado (`Ctrl + ~`)**, execute o comando:
   ```sh
   dotnet new console -n OutlookEmailReader
   ```
   Isso criará um novo projeto chamado `OutlookEmailReader`.

3. **Entre no diretório do projeto**:
   ```sh
   cd OutlookEmailReader
   ```

4. **Abra o projeto no VS Code**:
   ```sh
   code .
   ```

### 3. Usando o GitHub Copilot para Conectar ao Outlook

1. No **Explorer**, abra o arquivo `Program.cs`.
2. No início do arquivo, digite o seguinte comentário:
   ```csharp
   // Criar um programa em C# para conectar ao Outlook e listar os últimos X e-mails recebidos e enviados.
   ```
3. **Aguarde a sugestão do Copilot** e pressione **Tab** para aceitar o código gerado.

O código sugerido pelo Copilot pode ser semelhante a este (usando **IMAP via MailKit**):

```csharp
using System;
using MailKit.Net.Imap;
using MailKit.Search;
using MailKit;
using MimeKit;

class Program
{
    static void Main()
    {
        string host = "imap-mail.outlook.com"; // Servidor IMAP do Outlook
        int port = 993;
        string email = "seu-email@outlook.com";
        string senha = "sua-senha";

        using (var client = new ImapClient())
        {
            client.Connect(host, port, true);
            client.Authenticate(email, senha);

            var inbox = client.Inbox;
            inbox.Open(FolderAccess.ReadOnly);

            Console.WriteLine("Últimos e-mails recebidos:");
            foreach (var uid in inbox.Search(SearchQuery.All).TakeLast(5)) // Últimos 5 e-mails
            {
                var message = inbox.GetMessage(uid);
                Console.WriteLine($"Assunto: {message.Subject}, Data: {message.Date}");
            }

            var sent = client.GetFolder(SpecialFolder.Sent);
            sent.Open(FolderAccess.ReadOnly);

            Console.WriteLine("\nÚltimos e-mails enviados:");
            foreach (var uid in sent.Search(SearchQuery.All).TakeLast(5)) // Últimos 5 enviados
            {
                var message = sent.GetMessage(uid);
                Console.WriteLine($"Assunto: {message.Subject}, Data: {message.Date}");
            }

            client.Disconnect(true);
        }
    }
}
```

4. **Salve o arquivo (`Ctrl + S`).**

5. **Adicione o pacote MailKit ao projeto**, executando:
   ```sh
   dotnet add package MailKit
   ```

### 4. Testando o Código

1. No terminal do VS Code, execute:
   ```sh
   dotnet run
   ```
2. O console deve exibir os **últimos 5 e-mails recebidos e enviados** com **assunto e data**.

### 5. Usando o GitHub Copilot Chat para Modificar o Código

Agora, vamos **pedir ao GitHub Copilot Chat para incluir a data da resposta do usuário (se existir)**.

1. **Abra o painel do Copilot Chat** (`Ctrl + Shift + I` ou clique no ícone do Copilot Chat).
2. No chat, digite o seguinte comando:
   ```plaintext
   Modifique o código para que a lista de e-mails recebidos inclua a data da minha resposta, caso eu tenha respondido.
   ```
3. **Aguarde a sugestão do Copilot** e copie o código gerado.
4. **Cole a versão atualizada no `Program.cs` e salve (`Ctrl + S`).**

O Copilot deve gerar um código atualizado que verifica se o e-mail foi respondido, possivelmente usando o cabeçalho **"In-Reply-To"**.

### 6. Testando a Nova Versão

1. No terminal do VS Code, execute:
   ```sh
   dotnet run
   ```
2. Agora, os **e-mails recebidos mostrarão a data da resposta** (se houver).

## Conclusão

Agora você aprendeu a **utilizar o GitHub Copilot** e o **GitHub Copilot Chat** para gerar e modificar código automaticamente, conectando-se ao **Outlook** para obter informações dos e-mails recebidos e enviados.

Esse recurso pode ser útil para automatizar consultas a caixas de e-mails e analisar comunicações.

> **obs.:** *conteúdo parcialmente gerado por IA*
