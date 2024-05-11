## RETO N°8 100 DAYS OF PROYECTS 

### 08-nft-preview-card-component

<img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1714250855384/e0041611-30f4-4b47-ace9-b1080aac61da.jpeg?auto=compress,format&format=webp" alt="Texto alternativo" width="800"/>

### Tecnologias
[![HTML](https://img.shields.io/badge/HTML5-orange?style=flat&logo=html5)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
[![CSS](https://img.shields.io/badge/CSS3-blue?style=flat&logo=css3)](https://developer.mozilla.org/en-US/docs/Web/CSS)

### Ver demo

[Demo](https://lohanao.github.io/08-nft-preview-card-component/)

## Desafio
Nuestra misión será crear un componente NFT vista previa con efecto overlay, usando HTML y CSS; y lograr que se parezca lo más posible al diseño.

### Los usuarios deberían poder:
1-Ver un diseño óptimo en pantallas grandes(1200px) y pequeñas(375px).

2-Ver una imagen de fondo(overlay) al pasar el mouse sobre la tarjeta.

3-Ver un color diferente(hover) al pasar el mouse sobre el título de tarjeta y nombre del usuario.

### Importante:

Agrega un icono favicon al proyecto.

Agrega una URL fácil de recordar (ej. 08-nft-preview-card-component).

Agrega un título al proyecto (ej. NFT Preview Card Component - Frontend Club).

Bonus: Agrega un archivo readme.md al proyecto.

## Solución
### Resolución con HTML y CSS
En este proyecto, utilicé HTML y CSS para crear una tarjeta de codigo QR que muestra una imagen con un código Qr, un titulo y una descripción.

### Estructura HTML
El contenido de la tarjeta de código QR se estructuró utilizando elementos HTML semánticos para mejorar la accesibilidad y el SEO del sitio web. A continuación se muestra una vista general de la estructura HTML utilizada:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="css/style.css">
    <link rel="shortcut icon" href="images/favicon-32x32.png" type="image/png">
    <title> NFT Preview Card Component - Frontend Club</title>
</head>
<body>
    <main class="container">
        <article class="card">
            <div class="image-container">
            <img class="image-eq" src="images/image-equilibrium.jpg" alt="img equilibrium">
            <div class="overlay">
                <img src="images/icon-view.svg" alt="icon-view">
            </div>
        </div>
            <h2>Equilibrium #3429</h2>
            <p class="description">Our Equilibrium collection promotes balance and calm.</p>
            <div class="content">
            <div class="price">
                <img src="images/icon-ethereum.svg" alt="icon-ethereum">
                <p>0.041 ETH</p>
            </div>
            <div class="time">
                <img src="images/icon-clock.svg" alt="icon-clock">
                <p>3 days left</p>
            </div>
        </div>
            <div class="footer">
                <img src="images/image-avatar.png" alt="image-avatar">
                <p>Creation of <span>Jules Wyvern</span></p>
            </div>

        </article>

    </main>
    
</body>
</html>
```


Para lograr el diseño deseado de la tarjeta de producto, sigue estos pasos:

### Definir estilos básicos para el contenedor y la tarjeta:
#### El contenedor debe tener un estilo para centrar su contenido verticalmente y horizontalmente. Puedes lograr esto use display: flex, justify-content: center y align-items: center.
#### Use los siguientes estilos CSS le di un ancho maximo a la tarjeta para evitar usar medias queries e a la imagen le aplique un efecto overlay al hacer hover en la imagen.
```
@import url("https://fonts.googleapis.com/css2?family=Outfit:wght@100..900&display=swap");
:root {
  /* Colors primary */
  --Soft-blue: hsl(215, 51%, 70%);
  --Cyan: hsl(178, 100%, 50%);

  /* Neutral */
  --Very-dark-blue1: hsl(217, 54%, 11%);
  --Very-dark-blue2: hsl(216, 50%, 16%);
  --Very-dark-blue3: hsl(215, 32%, 27%);
  --White: hsl(0, 0%, 100%);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Outfit", sans-serif;
  background-color: var(--Very-dark-blue1);
  font-size: 18px;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  height: 100vh;
}

.card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: var(--Very-dark-blue2);
  border-radius: 20px;
  max-width: 350px;
  padding: 20px;
  box-shadow: 0 0 20px 5px rgba(0, 0, 0, 0.5);
}

.image-container {
  position: relative;
  width: 100%;
  border-radius: 10px;

}


.image-eq {
  width: 100%;
  border-radius: 10px;
}
.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 98%;
  border-radius: 10px;
  opacity: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0,255,247,0.5);
  transition: all 1s ease-in-out;
}

.image-container:hover .overlay {
  cursor: pointer;
  opacity: 1;
}
.overlay > img {
  width: 50px;
  height: auto;
  
}

h2 {
  width: 100%;
  color: var(--White);
  margin: 20px 0;
  text-align: start;
  transition: all 1s ease-in-out;
}

h2:hover {
  color: var(--Cyan);
  cursor: pointer;
}

.description {
  color: var(--Soft-blue);
  text-align: start;
  line-height: 1.5;
}

.content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  border-bottom: solid 1px var(--Very-dark-blue3);
}
.price {
  display: flex;
  align-items: center;
  gap: 10px;
  margin: 20px 0;
}

.price p {
  color: var(--Cyan);
}

.time {
  display: flex;
  align-items: center;
  gap: 10px;
}

.time p {
  color: var(--Soft-blue);
}

.footer {
  display: flex;
  align-items: center;
  gap: 15px;
  margin: 20px 0;
  width: 100%;
}

.footer img {
  width: 30px;
  border-radius: 50%;
  border: 1px solid var(--White);
}

.footer p {
  color: var(--Soft-blue);
}

.footer span {
  color: var(--White);
  transition: all 1s ease-in-out;
}

.footer span:hover {
  color: var(--Cyan);
  cursor: pointer;
}


 ```

## Conclusiones
En conclusión, la creación de esta tarjeta  fue un ejercicio interesante para practicar mis habilidades en HTML y CSS sobre todo overlay a la imagen. Espero que este README te haya proporcionado una buena comprensión del proyecto y de mi proceso de desarrollo.

¡Gracias por revisar mi proyecto!

Para cualquier pregunta o comentario, no dudes en contactarme a través de mi correo electrónico: lohaorellano13@gmail.com
