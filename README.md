# 🎉 Amigo-secreto-sorteador 🎁

### O Sorteio de Amigo Secreto Nunca Foi Tão Divertido! 🎊

Chegou o **Amigo-secreto-sorteador**, a aplicação perfeita para quem quer fazer o sorteio do amigo secreto de uma maneira prática, rápida e, claro, divertida! Com apenas alguns cliques, você vai poder adicionar todos os participantes e, em segundos, descobrir quem é o presenteado de quem. Só para ressaltar, é exigido um minímo de **4 pessoas**.

✨ **Características principais**:
- **Adicionar amigos**: Simples e rápido! Basta digitar o nome (sem ser repetido) e adicionar ao sorteio.
- **Sorteio aleatório**: A mágica acontece aqui! Com um clique, o sistema embaralha os nomes e mostra o resultado para todos.
- **Reiniciar tudo**: Comece do zero com um simples clique. Nada de preocupação com dados antigos!

---

## 🛠️ Tecnologias Usadas

- **HTML**: Para a estrutura simples e eficiente.
- **CSS**: Estilo básico para deixar o layout bacana.
- **JavaScript**: A cereja do bolo, com a lógica do sorteio e interação com a página.

---

## 🚀 Como Usar

1. **Adicione os Participantes**: Vá até a caixa de entrada e insira o nome dos amigos. Simples assim! 📝
2. **Clique em "Sortear"**: O sistema embaralha tudo para garantir que o sorteio seja 100% aleatório! 🔄
3. **Veja o Resultado**: O amigo secreto de cada participante aparece de forma super clara na tela. 👀
4. **Reinicie**: Precisa começar de novo? Clique em "Reiniciar" e tudo será limpo! 🔁

---

## 🎯 Funcionalidades

### 📝 **Adicionar Amigos**

Basta digitar o nome de cada amigo na caixa de texto e clicar no botão "Adicionar". Cada nome será adicionado à lista de amigos que participam do sorteio.

### 🎲 **Sortear**

Com todos os nomes adicionados, basta clicar em "Sortear". O sistema embaralha os nomes e cria os pares para o amigo secreto de cada pessoa. A magia do sorteio acontece automaticamente!

### 🔄 **Reiniciar**

Cansou de ver o sorteio? Não tem problema! O botão "Reiniciar" limpa todas as listas e permite que você comece do zero.

---

## 🔍 Como Funciona o Código?

O projeto é bem simples, mas altamente funcional! A lógica está em três funções principais que trabalham juntas para criar o sorteio:

### **1. Adicionar Amigos**
A função adicionar pega o nome do amigo digitalizado, adiciona à lista e atualiza a exibição na tela.

```javascript
function adicionar() {
    let nome = document.getElementById('nome-amigo');

    if (nome.value == '') {
        alert('Informe o nome do amigo!');
        return;
    }

    if (amigos.includes(nome.value)) {
        alert('Nome já adicionado. É necessário diferenciar os nomes para prosseguirmos');
        return;
    }
    
    let lista = document.getElementById('lista-amigos');
    amigos.push(nome.value);

    if (lista.textContent == '') {
        lista.textContent = nome.value;
    } else {
        lista.textContent = lista.textContent + ', ' + nome.value;
    }
    nome.value = '';
}
```

### **2. Sortear os Amigos**
A função sortear embaralha os nomes e exibe o resultado na tela, mostrando quem é amigo de quem.

```javascript
function sortear() {
    if (amigos.length < 4) {
        alert('Adicione no mínimo 4 amigos!');
        return;
    }

    embaralha(amigos);
    let sorteio = document.getElementById('lista-sorteio');
    
    for (let i = 0; i < amigos.length; i++) {
        
        if (i == amigos.length - 1) {
            sorteio.innerHTML = sorteio.innerHTML + amigos[i] + '-->' + amigos[0] + '<br>';
        } else {
            sorteio.innerHTML = sorteio.innerHTML + amigos[i] + '-->' + amigos[i + 1] + '<br>';
        }
    }
    
}
```
### **3. Embaralhar uma Lista de Amigos**
O algoritmo de embaralhamento é feito com o método Fisher-Yates, garantindo uma distribuição aleatória dos participantes.

```javascript
function embaralha(lista) {

    for (let indice = lista.length; indice; indice--) {

        const indiceAleatorio = Math.floor(Math.random() * indice);

        // atribuição via destructuring
        [lista[indice - 1], lista[indiceAleatorio]] = 
            [lista[indiceAleatorio], lista[indice - 1]];
    }
}
```
### **4. Reiniciar o Sorteio**]
A função reiniciar limpa as listas de amigos e o resultado do sorteio, permitindo que o usuário comece tudo de novo com um clique.

```javascript
function reiniciar() {
    amigos = [];
    document.getElementById('lista-amigos').innerHTML = '';
    document.getElementById('lista-sorteio').innerHTML = '';
}
```
---
## 🎓 O que você vai aprender com este projeto?

Este projeto simples oferece uma excelente oportunidade para aprender conceitos fundamentais de JavaScript, como:

- **Manipulação de Arrays**: Usamos arrays para armazenar e manipular os nomes dos participantes.
- **Funções**: Como criar funções para adicionar dados, embaralhar e exibir resultados.
- **Manipulação do DOM**: Aprenda a interagir com os elementos da página usando `innerHTML` e `textContent`.
- **Laços de Repetição**: Usamos o `for` para iterar sobre os arrays e gerar o sorteio.
- **Eventos**: Como responder às interações do usuário com botões e entradas.

---
## 🤝 Contribua Com o Projeto

Quer melhorar o **Amigo-secreto-sorteador** ou adicionar novas funcionalidades? Adoro contribuições!

- Faça um **fork** deste repositório.
- Crie uma nova **branch** para suas modificações.
- Envie uma **pull request** para discutirmos suas mudanças.

---

### 📜 Licença

Este projeto está licenciado sob uma licença do **MIT**.

---

Adivinha o que vem agora? Divirta-se com o seu sorteio de amigo secreto! 🥳
