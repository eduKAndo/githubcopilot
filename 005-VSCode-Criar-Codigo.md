# Exercício: Utilizando o GitHub Copilot para gerar código em C# no VS Code

## Objetivo
Neste exercício, você irá utilizar o **GitHub Copilot** para gerar código  automaticamente num projeto C# dentro do **Visual Studio Code**, aproveitando seu poder de sugestão para acelerar o desenvolvimento.

## Passo a Passo

### 1. Configurando o Ambiente
Antes de começar, certifique-se de que possui:
- **Visual Studio Code** instalado ([Download](https://code.visualstudio.com/))
- **Extensão do C#** instalada no VS Code
- **.NET SDK** instalado ([Download](https://dotnet.microsoft.com/en-us/download))
- **GitHub Copilot** instalado e autenticado ([Guia de Instalação](https://github.com/features/copilot))

Se ainda não instalou o **GitHub Copilot** no VS Code, siga o [passo a passo de instalação](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot).

### 2. Criando um Novo Projeto C# no VS Code
1. Abra o **VS Code**.
2. No terminal integrado (`Ctrl + ~`), execute o comando:
   ```sh
   dotnet new console -n CopilotExample
   ```
   Esse comando cria um novo projeto C# chamado `CopilotExample`.

3. Entre no diretório do projeto:
   ```sh
   cd CopilotExample
   ```

4. Abra o projeto no VS Code:
   ```sh
   code .
   ```

### 3. Usando o GitHub Copilot para Gerar Código Novo
1. No **Explorer** do VS Code, abra o arquivo `Program.cs`.
2. Apague qualquer código existente e, no arquivo vazio, digite o seguinte comentário:
   ```csharp
   // Criar uma classe chamada Calculadora com métodos para soma, subtração, multiplicação e divisão.
   ```
3. **Aguarde alguns segundos** e observe as sugestões automáticas do GitHub Copilot.
4. Pressione **Tab** para aceitar a sugestão gerada.
5. Se necessário, modifique o comentário para direcionar melhor a geração do código.

### 4. Executando o Código Gerado
Se o GitHub Copilot gerou uma classe `Calculadora`, complete o código para testar:

```csharp
using System;

class Program
{
    static void Main()
    {
        Calculadora calc = new Calculadora();
        Console.WriteLine("Soma: " + calc.Somar(5, 3));
        Console.WriteLine("Subtração: " + calc.Subtrair(10, 4));
        Console.WriteLine("Multiplicação: " + calc.Multiplicar(6, 2));
        Console.WriteLine("Divisão: " + calc.Dividir(8, 2));
    }
}

class Calculadora
{
    public int Somar(int a, int b) => a + b;
    public int Subtrair(int a, int b) => a - b;
    public int Multiplicar(int a, int b) => a * b;
    public double Dividir(double a, double b) => b != 0 ? a / b : throw new DivideByZeroException();
}
```

1. Salve o arquivo (`Ctrl + S`).
2. No terminal, execute o programa:
   ```sh
   dotnet run
   ```
3. Observe a saída no console, que deverá exibir os resultados das operações matemáticas.

## Conclusão
Agora você experimentou como o **GitHub Copilot** pode **gerar código automaticamente** baseado em descrições textuais. Esse recurso pode ser utilizado para acelerar o desenvolvimento e obter sugestões inteligentes de código.

Para aprofundar-se mais no uso do GitHub Copilot, explore sua documentação oficial:  
[https://github.com/features/copilot](https://github.com/features/copilot)

> **obs.:** *conteúdo parcialmente gerado por IA*
