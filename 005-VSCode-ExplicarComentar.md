# Exercício: Usando o GitHub Copilot para explicar e comentar código C# no VS Code

## Objetivo
Neste exercício, você aprenderá a utilizar o **GitHub Copilot** para **gerar explicações e comentários automaticamente** em um código C# dentro do **Visual Studio Code**. O Copilot pode ajudar a documentar seu código com descrições claras, facilitando a compreensão para outros desenvolvedores e para você mesmo no futuro.

## Passo a Passo

### 1. Configurando o Ambiente
Antes de começar, certifique-se de que possui:
- **Visual Studio Code** instalado ([Download](https://code.visualstudio.com/))
- **Extensão do C#** instalada no VS Code
- **.NET SDK** instalado ([Download](https://dotnet.microsoft.com/en-us/download))
- **GitHub Copilot** instalado e autenticado ([Guia de Instalação](https://github.com/features/copilot))

Se ainda não instalou o **GitHub Copilot** no VS Code, siga o [passo a passo de instalação](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot).

### 2. Criando um Novo Arquivo C# no VS Code
1. Abra o **VS Code**.
2. Crie um novo arquivo chamado **`Program.cs`**.
3. Copie e cole o seguinte código **sem comentários**:

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

4. Salve o arquivo (`Ctrl + S`).

### 3. Usando o GitHub Copilot para Gerar Comentários
Agora, vamos **usar o GitHub Copilot para gerar automaticamente explicações e comentários** para o código acima.

1. **Ative o GitHub Copilot**: Certifique-se de que o Copilot está ativo e funcional no VS Code.
2. **Peça para o Copilot gerar explicações**: No início do arquivo `Program.cs`, adicione o seguinte comentário e aguarde o Copilot sugerir descrições:

   ```csharp
   // Explique este código e adicione comentários em cada parte.
   ```

3. **Aguarde a sugestão do Copilot** e pressione **Tab** para aceitar.

4. Se necessário, refine o pedido alterando o comentário para algo mais específico, como:

   ```csharp
   // Adicione comentários explicativos a este código.
   ```

### 4. Código Final com Comentários Gerados pelo GitHub Copilot

Após aceitar as sugestões do Copilot, o código pode ficar assim:

```csharp
using System; // Biblioteca para entrada e saída no console

// Classe principal do programa
class Program
{
    static void Main()
    {
        // Criando uma instância da classe Calculadora
        Calculadora calc = new Calculadora();

        // Chamando os métodos da calculadora e exibindo os resultados no console
        Console.WriteLine("Soma: " + calc.Somar(5, 3));            // Soma 5 + 3
        Console.WriteLine("Subtração: " + calc.Subtrair(10, 4));   // Subtrai 10 - 4
        Console.WriteLine("Multiplicação: " + calc.Multiplicar(6, 2)); // Multiplica 6 * 2
        Console.WriteLine("Divisão: " + calc.Dividir(8, 2));       // Divide 8 / 2
    }
}

// Classe responsável por operações matemáticas
class Calculadora
{
    // Método para somar dois números inteiros
    public int Somar(int a, int b) => a + b;

    // Método para subtrair dois números inteiros
    public int Subtrair(int a, int b) => a - b;

    // Método para multiplicar dois números inteiros
    public int Multiplicar(int a, int b) => a * b;

    // Método para dividir dois números, evitando erro de divisão por zero
    public double Dividir(double a, double b) => 
        b != 0 ? a / b : throw new DivideByZeroException();
}
```

### 5. Testando o Código Comentado
1. No terminal integrado do VS Code, execute:
   ```sh
   dotnet run
   ```
2. Verifique os resultados e veja como os comentários ajudam a entender o funcionamento do código.

## Conclusão
Agora você aprendeu a **utilizar o GitHub Copilot para explicar e comentar código automaticamente**. Isso pode ser muito útil para documentar seu código e facilitar a colaboração com outros desenvolvedores.

Sempre que precisar de explicações, basta adicionar um comentário no código solicitando ao Copilot para gerar descrições.

> **obs.:** *conteúdo parcialmente gerado por IA*
