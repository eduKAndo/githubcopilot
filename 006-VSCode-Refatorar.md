# Exercício: Usando o GitHub Copilot para refatorar código - transformação entre funções recursivas e iterativas

## Objetivo
Neste exercício, você aprenderá a **utilizar o GitHub Copilot para refatorar código**, convertendo uma função **recursiva em iterativa** e vice-versa. O Copilot pode sugerir diferentes abordagens para melhorar o desempenho e legibilidade do código.

## Passo a Passo

### 1. Configurando o Ambiente
Antes de começar, certifique-se de que possui:
- **Visual Studio Code** instalado ([Download](https://code.visualstudio.com/))
- **Extensão do Python** instalada no VS Code
- **GitHub Copilot** instalado e autenticado ([Guia de Instalação](https://github.com/features/copilot))
- **Python 3** instalado ([Download](https://www.python.org/downloads/))

Se ainda não instalou o **GitHub Copilot** no VS Code, siga o [passo a passo de instalação](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot).

### 2. Criando o Arquivo de Código

1. Abra o **VS Code**.
2. Crie um novo arquivo chamado **`recursivo_iterativo.py`**.
3. Copie e cole a seguinte função recursiva para calcular o fatorial:

```python
def fatorial_recursivo(n):
    if n == 0 or n == 1:
        return 1
    return n * fatorial_recursivo(n - 1)

print(fatorial_recursivo(5))  # Saída esperada: 120
```

4. Salve o arquivo (`Ctrl + S`).

### 3. Usando o GitHub Copilot para Refatorar o Código

Agora, vamos **pedir ao GitHub Copilot para refatorar essa função recursiva para uma versão iterativa**:

1. No início do arquivo, adicione o seguinte comentário:
   ```python
   # Refatore esta função para que ela seja iterativa em vez de recursiva.
   ```

2. **Aguarde a sugestão do Copilot** e pressione **Tab** para aceitar a refatoração.

3. O código gerado pelo Copilot deve ser semelhante a este:

```python
def fatorial_iterativo(n):
    resultado = 1
    for i in range(2, n + 1):
        resultado *= i
    return resultado

print(fatorial_iterativo(5))  # Saída esperada: 120
```

### 4. Transformando uma Função Iterativa em Recursiva

Agora, faremos o inverso. Usaremos o Copilot para transformar uma função iterativa da sequência de Fibonacci em uma versão recursiva.

1. Copie e cole a seguinte função iterativa:

```python
def fibonacci_iterativo(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    
    a, b = 0, 1
    for _ in range(2, n + 1):
        a, b = b, a + b
    return b

print(fibonacci_iterativo(6))  # Saída esperada: 8
```

2. Acima da função, adicione o seguinte comentário:
   ```python
   # Transforme esta função iterativa em uma versão recursiva.
   ```

3. **Aguarde a sugestão do Copilot** e pressione **Tab** para aceitar.

4. O código gerado pelo Copilot deve ser semelhante a este:

```python
def fibonacci_recursivo(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    return fibonacci_recursivo(n - 1) + fibonacci_recursivo(n - 2)

print(fibonacci_recursivo(6))  # Saída esperada: 8
```

### 5. Testando o Código Refatorado

1. No terminal integrado do VS Code, execute:
   ```sh
   python recursivo_iterativo.py
   ```
2. Verifique os resultados e veja como o Copilot ajudou a converter a função de uma abordagem para outra.

## Conclusão

Agora você aprendeu a **utilizar o GitHub Copilot para refatorar código automaticamente**, convertendo funções **recursivas em iterativas** e vice-versa. Essa técnica pode ser útil para melhorar a eficiência do código e explorar diferentes formas de resolver problemas computacionais.

> **obs.:** *conteúdo parcialmente gerado por IA*
