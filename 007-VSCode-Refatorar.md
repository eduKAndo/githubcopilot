# Exercício: Usando o GitHub Copilot Chat para traduzir código entre linguagens

## Objetivo
Neste exercício, você aprenderá a **utilizar o GitHub Copilot Chat** para traduzir uma função de **Python para C#**. Essa funcionalidade pode ser útil ao migrar código entre diferentes linguagens de programação.

## Passo a Passo

### 1. Configurando o Ambiente
Antes de começar, certifique-se de que possui:
- **Visual Studio Code** instalado ([Download](https://code.visualstudio.com/))
- **Extensão do Python e do C#** instalada no VS Code
- **GitHub Copilot e Copilot Chat** instalados e autenticados ([Guia de Instalação](https://github.com/features/copilot))
- **Python 3 e .NET SDK** instalados ([Python](https://www.python.org/downloads/) | [.NET](https://dotnet.microsoft.com/en-us/download))

Se ainda não instalou o **GitHub Copilot Chat**, siga o [passo a passo de instalação](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat).

### 2. Criando o Arquivo de Código

1. Abra o **VS Code**.
2. Crie um novo arquivo chamado **`fibonacci.py`**.
3. Copie e cole a seguinte função recursiva para calcular Fibonacci em Python:

```python
def fibonacci_recursivo(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    return fibonacci_recursivo(n - 1) + fibonacci_recursivo(n - 2)

print(fibonacci_recursivo(6))  # Saída esperada: 8
```

4. Salve o arquivo (`Ctrl + S`).

### 3. Usando o GitHub Copilot Chat para Traduzir Código

Agora, vamos **pedir ao GitHub Copilot Chat para converter essa função de Python para C#**:

1. **Abra o painel do Copilot Chat** no VS Code (`Ctrl + Shift + I` ou clique no ícone do Copilot Chat).
2. No chat, digite o seguinte comando:
   ```plaintext
   Converta a seguinte função de Python para C#:

   def fibonacci_recursivo(n):
       if n == 0:
           return 0
       elif n == 1:
           return 1
       return fibonacci_recursivo(n - 1) + fibonacci_recursivo(n - 2)
   ```

3. **Aguarde a resposta do Copilot** e copie o código sugerido.

4. Crie um novo arquivo chamado **`fibonacci.cs`** e cole o código gerado.

### 4. Código Traduzido para C# (Sugestão do Copilot Chat)

O Copilot deve gerar um código semelhante a este:

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine(FibonacciRecursivo(6)); // Saída esperada: 8
    }

    static int FibonacciRecursivo(int n)
    {
        if (n == 0) return 0;
        if (n == 1) return 1;
        return FibonacciRecursivo(n - 1) + FibonacciRecursivo(n - 2);
    }
}
```

5. Salve o arquivo (`Ctrl + S`).

### 5. Testando o Código Traduzido

1. No terminal do VS Code, execute:
   ```sh
   dotnet run fibonacci.cs
   ```
2. Compare os resultados com a versão original em Python para garantir que ambas produzem o mesmo valor.

## Conclusão

Agora você aprendeu a **utilizar o GitHub Copilot Chat para traduzir código automaticamente** entre diferentes linguagens. Esse recurso pode ser útil ao trabalhar em projetos multi-linguagem ou ao portar funcionalidades para novas plataformas.

> **obs.:** *conteúdo parcialmente gerado por IA*
