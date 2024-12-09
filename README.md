# **Documentação: Método `replace` em JavaScript**

O método `replace` é usado para localizar e substituir partes específicas de uma string. Ele é amplamente utilizado em manipulação de texto, como para corrigir frases, aplicar formatações ou processar entradas de usuários.

---

## **Descrição**

- O método retorna uma **nova string** com a substituição realizada.
- A string original **não é alterada**.
- Suporta **strings** ou **expressões regulares** para a busca, e **strings** ou **funções** para o texto substituto.

---

## **Sintaxe**

```javascript
string.replace(padrão, substituto);
```

### **Parâmetros**

1. **`padrão`** (obrigatório):
   - Define o que será substituído.
   - Pode ser:
     - Uma **string**: substitui a primeira ocorrência.
     - Uma **expressão regular**: oferece mais controle, como substituições globais ou condicionais.

2. **`substituto`** (obrigatório):
   - Define o que substituirá o padrão encontrado.
   - Pode ser:
     - Uma **string**: substituto fixo.
     - Uma **função**: substituto dinâmico, com base na lógica implementada.

---

## **Retorno**
- Uma nova string com as substituições aplicadas.

---

## **Exemplos**

### **Substituição simples com strings**

```javascript
const frase = "Eu amo programação.";
const novaFrase = frase.replace("programação", "JavaScript");
console.log(novaFrase);
// Saída: "Eu amo JavaScript."
```

### **Substituição com expressão regular**

```javascript
const frase = "O carro é rápido, e o carro é caro.";
const novaFrase = frase.replace(/carro/g, "moto");
console.log(novaFrase);
// Saída: "O moto é rápido, e o moto é caro."
```

### **Substituição com função dinâmica**

```javascript
const texto = "A1, B2, C3";
const novoTexto = texto.replace(/\d/g, (numero) => {
  return parseInt(numero) * 2;
});
console.log(novoTexto);
// Saída: "A2, B4, C6"
```

### **Usando substituições especiais em strings**
O método `replace` suporta tokens especiais para referências na string substituta:

| Token | Descrição                                    |
|-------|---------------------------------------------|
| `$&`  | Correspondência completa com o padrão.      |
| ``$` `` | Parte antes da correspondência.           |
| `$'`  | Parte após a correspondência.              |
| `$n`  | Captura do grupo *n* em expressões regulares. |

Exemplo:

```javascript
const frase = "Olá mundo!";
const novaFrase = frase.replace(/(mundo)/, "querido $&");
console.log(novaFrase);
// Saída: "Olá querido mundo!"
```

---

## **Notas Importantes**

1. **Substituições Globais**: Para substituir todas as ocorrências, use o modificador `g` com uma expressão regular.
2. **Case Sensitivity**: O método é sensível a maiúsculas e minúsculas. Para ignorar diferenças de caixa, use o modificador `i`.
3. **Strings Imutáveis**: Como strings são imutáveis em JavaScript, sempre guarde o resultado em uma nova variável.
