
# 🐾 Atividade Prática: Desenho Interativo de um Cachorro no Canvas

Nesta atividade, você criará uma aplicação interativa que, ao clicar em um botão, desenha um cachorro em uma tag `<canvas>`. A atividade permite explorar as capacidades do HTML5 e JavaScript, especialmente as funções de desenho em canvas.

---

## 🎯 Requisitos

1. **Função de Desenho**:
   - Crie uma função em **JavaScript** que desenhe o cachorro no elemento `<canvas>`.
   
2. **Interatividade**:
   - A função deve ser chamada ao clicar em um botão, link ou outro elemento interativo.

3. **Estrutura do Desenho**:
   - O desenho do cachorro deve incluir pelo menos:
     - Cabeça
     - Corpo
     - Pernas
     - Orelhas
     - Cauda

4. **Canvas**:
   - Utilize métodos do contexto 2D do canvas para desenhar diferentes formas geométricas que compõem o cachorro.

---

## 🌟 Desafio

- Adicione detalhes específicos ao cachorro, como:
  - **Olhos**, **nariz**, **boca**, etc.
- Utilize cores criativas para tornar o desenho mais interessante e expressivo.
- Experimente criar um estilo único para o cachorro (cartoon, minimalista, realista).

---

## 📦 Entrega

1. **Formato do Arquivo**:
   - Entregue o código-fonte em um único arquivo HTML, contendo:
     - A tag `<style>` para os estilos.
     - A tag `<script>` para o código JavaScript.

2. **Descrição do Projeto**:
   - Forneça uma breve explicação no início do arquivo ou como comentário descrevendo:
     - As escolhas de design para o cachorro.
     - Como o usuário interage com a aplicação.

---

## 📝 Avaliação

1. **Representação Visual**:
   - Clareza e fidelidade das formas que representam o cachorro.

2. **Interatividade**:
   - Como o botão ou objeto interativo chama a função e desenha o cachorro.

3. **Criatividade**:
   - Uso de cores, formas e detalhes que tornam o desenho único.

4. **Qualidade do Código**:
   - Organização, legibilidade e uso eficiente de funções JavaScript.

5. **Explicação das Decisões**:
   - Capacidade de justificar as escolhas de design e implementação.

---

## 🔧 Estrutura Básica do Código

Exemplo de estrutura inicial:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Desenho Interativo: Cachorro</title>
    <style>
        canvas {
            border: 1px solid #000;
            display: block;
            margin: 20px auto;
        }
        button {
            display: block;
            margin: 0 auto;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Desenho Interativo de um Cachorro</h1>
    <canvas id="canvas" width="400" height="400"></canvas>
    <button id="drawButton">Desenhar Cachorro</button>
    <script>
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');

        function desenharCachorro() {
            // Cabeça
            ctx.beginPath();
            ctx.arc(200, 120, 50, 0, Math.PI * 2); // Cabeça
            ctx.fillStyle = '#d4a373';
            ctx.fill();

            // Corpo
            ctx.beginPath();
            ctx.ellipse(200, 250, 80, 120, 0, 0, Math.PI * 2); // Corpo
            ctx.fillStyle = '#d4a373';
            ctx.fill();

            // Pernas
            ctx.fillStyle = '#8b5e3c';
            ctx.fillRect(140, 320, 30, 80); // Perna esquerda
            ctx.fillRect(230, 320, 30, 80); // Perna direita

            // Orelhas
            ctx.beginPath();
            ctx.ellipse(150, 80, 20, 40, Math.PI / 4, 0, Math.PI * 2); // Orelha esquerda
            ctx.fillStyle = '#8b5e3c';
            ctx.fill();
            ctx.beginPath();
            ctx.ellipse(250, 80, 20, 40, -Math.PI / 4, 0, Math.PI * 2); // Orelha direita
            ctx.fill();

            // Cauda
            ctx.beginPath();
            ctx.moveTo(270, 180);
            ctx.quadraticCurveTo(350, 150, 270, 130); // Cauda curvada
            ctx.strokeStyle = '#8b5e3c';
            ctx.lineWidth = 8;
            ctx.stroke();

            // Detalhes
            ctx.beginPath();
            ctx.arc(185, 110, 5, 0, Math.PI * 2); // Olho esquerdo
            ctx.arc(215, 110, 5, 0, Math.PI * 2); // Olho direito
            ctx.fillStyle = '#000';
            ctx.fill();

            ctx.beginPath();
            ctx.arc(200, 140, 5, 0, Math.PI); // Nariz
            ctx.fillStyle = '#000';
            ctx.fill();
        }

        document.getElementById('drawButton').addEventListener('click', desenharCachorro);
    </script>
</body>
</html>
