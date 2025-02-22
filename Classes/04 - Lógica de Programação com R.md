
## 1. Tipos de Dados em R

Em R, os dados podem ser representados em diferentes tipos:

### 1.1 Tipos Básicos

- **Numérico (numeric)**: números decimais (ex: `3.14`, `2.0`)
- **Inteiro (integer)**: números inteiros (ex: `10L`, `-5L`)
- **Caracteres (character)**: texto (ex: `"R Programming"`)
- **Lógico (logical)**: valores booleanos (`TRUE`, `FALSE`)

### 1.2 Verificando e Convertendo Tipos

```r
x <- 10
class(x) # Verifica o tipo da variável

as.numeric("5") # Converte para numérico
as.character(10) # Converte para caractere
as.logical(0) # Converte para lógico (0 = FALSE, diferente de 0 = TRUE)
```

## 2. Estruturas de Dados em R

### 2.1 Vetores (Vectors)

Vetores são a estrutura de dados mais básica em R.

```r
vetor <- c(1, 2, 3, 4, 5)
vetor_texto <- c("a", "b", "c")
```

### 2.2 Matrizes (Matrices)

```r
matriz <- matrix(1:9, nrow=3, ncol=3)
```

### 2.3 Listas (Lists)

```r
lista <- list(nome="Pedro", idade=25, notas=c(8, 9, 10))
```

### 2.4 Data Frames

```r
df <- data.frame(Nome=c("Ana", "Bruno"), Idade=c(25, 30))
```

## 3. Estruturas de Controle

### 3.1 Condicionais (if-else)

```r
x <- 10
if (x > 5) {
  print("Maior que 5")
} else {
  print("Menor ou igual a 5")
}
```

### 3.2 Laços de Repetição

#### Loop for

```r
for (i in 1:5) {
  print(i)
}
```

#### Loop while

```r
x <- 1
while (x <= 5) {
  print(x)
  x <- x + 1
}
```

## 4. Funções em R

Funções são blocos de código reutilizáveis.

```r
soma <- function(a, b) {
  return(a + b)
}
resultado <- soma(5, 3)
print(resultado)
```

## 5. Exercícios

1 - Escreva uma função que leia um vetor de números e retorne TRUE ou FALSE para os números que forem pares.
2 - Crie um Loop para preencher uma matriz 10x10 com os números de 100 até 1, por linha.
3 - Crie uma segunda matriz com as 5 primeiras colunas e 4 ultimas colunas da criada matriz anteriormente.