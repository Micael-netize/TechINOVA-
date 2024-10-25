

*Arquivo:* index.php

```
<?php
// Conexão com o banco de dados
$host = 'localhost';
$usuario = 'seu_usuario';
$senha = 'sua_senha';
$banco = 'meu_banco';

$conexao = mysqli_connect($host, $usuario, $senha, $banco);

// Verifica conexão
if (!$conexao) {
    die("Erro ao conectar ao banco de dados: " . mysqli_connect_error());
}

// Cadastra livro
if ($_POST) {
    $titulo = $_POST['titulo'];
    $autor = $_POST['autor'];
    $ano = $_POST['ano'];

    $query = "INSERT INTO livros (titulo, autor, ano) VALUES ('$titulo', '$autor', $ano)";
    mysqli_query($conexao, $query);
}

// Fecha conexão
mysqli_close($conexao);
?>

<!DOCTYPE html>
<html>
<head>
    <title>Cadastro de Livros</title>
</head>
<body>
    <h1>Cadastro de Livros</h1>
    <form action="" method="post">
        <label for="titulo">Título:</label>
        <input type="text" id="titulo" name="titulo"><br><br>
        <label for="autor">Autor:</label>
        <input type="text" id="autor" name="autor"><br><br>
        <label for="ano">Ano:</label>
        <input type="number" id="ano" name="ano"><br><br>
        <input type="submit" value="Cadastrar">
    </form>
</body>
</html>
```

*Arquivo:* conexao.php

```
<?php
// Conexão com o banco de dados
$host = 'localhost';
$usuario = 'seu_usuario';
$senha = 'sua_senha';
$banco = 'meu_banco';

$conexao = mysqli_connect($host, $usuario, $senha, $banco);

// Verifica conexão
if (!$conexao) {
    die("Erro ao conectar ao banco de dados: " . mysqli_connect_error());
}
?>
```

*Banco de Dados:*

```
CREATE TABLE livros (
    id INT PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(255),
    autor VARCHAR(255),
    ano INT
);
```

