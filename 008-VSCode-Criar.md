# Exercício: Usando o GitHub Copilot para criar e estilizar uma página HTML com CSS

## Objetivo
Neste exercício, você aprenderá a **utilizar o GitHub Copilot para gerar automaticamente uma página HTML e seu estilo em CSS**. Vamos criar um **formulário de login** e estilizar sua aparência.

## Passo a Passo

### 1. Configurando o Ambiente
Antes de começar, certifique-se de que possui:
- **Visual Studio Code** instalado ([Download](https://code.visualstudio.com/))
- **Extensão do HTML e CSS** instalada no VS Code
- **GitHub Copilot** instalado e autenticado ([Guia de Instalação](https://github.com/features/copilot))

Se ainda não instalou o **GitHub Copilot**, siga o [passo a passo de instalação](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot).

### 2. Criando o Arquivo HTML

1. Abra o **VS Code**.
2. Crie um novo arquivo chamado **`index.html`**.
3. No início do arquivo, digite o seguinte comentário:
   ```html
   <!-- Crie um formulário de login com os controles 'usuário' e 'senha' e um link 'esqueci minha senha', além do botão 'enviar'. -->
   ```
4. **Aguarde a sugestão do Copilot** e pressione **Tab** para aceitar o código gerado.
5. O código sugerido pelo Copilot pode ser semelhante a este:

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="login-container">
        <h2>Login</h2>
        <form>
            <label for="usuario">Usuário:</label>
            <input type="text" id="usuario" name="usuario" required>

            <label for="senha">Senha:</label>
            <input type="password" id="senha" name="senha" required>

            <button type="submit">Entrar</button>

            <a href="#" class="esqueci-senha">Esqueci minha senha</a>
        </form>
    </div>
</body>
</html>
```

6. Salve o arquivo (`Ctrl + S`).

### 3. Criando o Arquivo de Estilização (CSS)

1. No VS Code, crie um novo arquivo chamado **`style.css`**.
2. No início do arquivo, digite o seguinte comentário:
   ```css
   /* Estilize o formulário de login */
   ```
3. **Aguarde a sugestão do Copilot** e pressione **Tab** para aceitar o código gerado.
4. O código sugerido pelo Copilot pode ser semelhante a este:

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.login-container {
    background: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    width: 300px;
}

h2 {
    margin-bottom: 20px;
}

input {
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    width: 100%;
    padding: 10px;
    background-color: #28a745;
    border: none;
    color: white;
    font-size: 16px;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #218838;
}

.esqueci-senha {
    display: block;
    margin-top: 10px;
    font-size: 14px;
    color: #007bff;
    text-decoration: none;
}

.esqueci-senha:hover {
    text-decoration: underline;
}
```

5. Salve o arquivo (`Ctrl + S`).

### 4. Visualizando o Resultado

1. No **Explorer** do VS Code, clique com o botão direito no arquivo **`index.html`** e selecione **"Open with Live Server"** (se a extensão estiver instalada) ou **abra o arquivo diretamente no navegador**.
2. Teste os campos do formulário e o link de recuperação de senha.

## Conclusão

Agora você aprendeu a **utilizar o GitHub Copilot para gerar páginas HTML e estilos CSS automaticamente**. Você pode ajustar o design conforme necessário e experimentar diferentes abordagens.

Experimente modificar o formulário e peça ao Copilot sugestões para aprimorar a aparência e a acessibilidade.

> **obs.:** *conteúdo parcialmente gerado por IA*
