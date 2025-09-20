<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carta de Cumpleaños</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(135deg, #000428, #004e92);
            padding: 20px;
            overflow-x: hidden;
        }

        .container {
            text-align: center;
            width: 100%;
            max-width: 500px;
        }

        .btn-primary {
            background: linear-gradient(45deg, #ff6b6b, #ff8e8e);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.2rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(255, 107, 107, 0.4);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 107, 107, 0.6);
        }

        .btn-primary:active {
            transform: translateY(1px);
        }

        .btn-primary::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transition: left 0.5s ease;
        }

        .btn-primary:hover::before {
            left: 100%;
        }

        .carta-container {
            display: none;
            perspective: 1000px;
            margin-top: 30px;
        }

        .carta {
            background: linear-gradient(135deg, #ffd1dc, #ffb6c1);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            position: relative;
            transform-style: preserve-3d;
            animation: aparecer 0.8s ease-out forwards;
            border: 3px solid #ff85a2;
        }

        @keyframes aparecer {
            0% {
                opacity: 0;
                transform: translateY(50px) rotateX(-30deg);
            }
            100% {
                opacity: 1;
                transform: translateY(0) rotateX(0);
            }
        }

        .carta::before {
            content: '❤️';
            position: absolute;
            top: -20px;
            right: -20px;
            font-size: 3rem;
            animation: flotar 3s ease-in-out infinite;
        }

        .carta::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80%;
            height: 10px;
            background: rgba(0, 0, 0, 0.2);
            border-radius: 50%;
            filter: blur(5px);
        }

        @keyframes flotar {
            0%, 100% {
                transform: translateY(0) rotate(0deg);
            }
            50% {
                transform: translateY(-10px) rotate(10deg);
            }
        }

        .corazon {
            position: absolute;
            font-size: 1.5rem;
            animation: caer 6s linear infinite;
        }

        @keyframes caer {
            0% {
                transform: translateY(-100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }

        .mensaje {
            color: #d63384;
            font-size: 1.1rem;
            line-height: 1.6;
            text-align: center;
            margin-bottom: 20px;
            font-weight: 500;
        }

        .titulo {
            color: #c2185b;
            font-size: 2rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            font-weight: bold;
        }

        .decoracion {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 20px 0;
        }

        .flor {
            font-size: 2rem;
            animation: girar 4s linear infinite;
        }

        @keyframes girar {
            0% {
                transform: rotate(0deg) scale(1);
            }
            50% {
                transform: rotate(180deg) scale(1.2);
            }
            100% {
                transform: rotate(360deg) scale(1);
            }
        }

        .firma {
            color: #e91e63;
            font-style: italic;
            font-weight: bold;
            margin-top: 20px;
            font-size: 1.2rem;
        }

        .confeti {
            position: fixed;
            width: 10px;
            height: 10px;
            background: linear-gradient(45deg, #ff6b6b, #ff8e8e, #ffd1dc, #ffb6c1);
            animation: confetiCaer 5s linear infinite;
            pointer-events: none;
        }

        @keyframes confetiCaer {
            0% {
                transform: translateY(-100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(720deg);
                opacity: 0;
            }
        }

        @media (max-width: 600px) {
            .carta {
                padding: 20px;
                margin: 0 10px;
            }
            
            .titulo {
                font-size: 1.5rem;
            }
            
            .mensaje {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <button class="btn-primary" onclick="mostrarCarta()">CLIK AQUI</button>
        
        <div class="carta-container" id="cartaContainer">
            <div class="carta">
                <h1 class="titulo">¡Feliz Día del Amor y la Amistad!</h1>
                
                <p class="mensaje">
                    Para mi mejor amiga,<br><br>
                    En este día especial quiero recordarte lo mucho que vales. 
                    Tu amistad es como un rayo de sol en los días grises, 
                    una luz que ilumina mi vida con alegría .<br><br>
                    Gracias por estar siempre ahí, por las risas compartidas, 
                    por los momentos inolvidables y por ser esa persona 
                    en quien siempre puedo confiar.<br><br>
                    ¡Que nuestra amistad siga creciendo  Eres increíble y te aprecio más 
                    de lo que las palabras pueden expresar.
                </p>
                
                <div class="decoracion">
                    <div class="flor">🌸</div>
                    <div class="flor" style="animation-delay: 1s;">🌹</div>
                    <div class="flor" style="animation-delay: 2s;">🌺</div>
                </div>
                
                <p class="firma">Con todo mi cariño,<br>Tu mejor amigo</p>
            </div>
        </div>
    </div>

    <script>
        function mostrarCarta() {
            const cartaContainer = document.getElementById('cartaContainer');
            const boton = document.querySelector('.btn-primary');
            
            // Ocultar botón
            boton.style.display = 'none';
            
            // Mostrar carta con animación
            cartaContainer.style.display = 'block';
            
            // Crear corazones flotantes
            crearCorazones();
            
            // Crear confeti
            crearConfeti();
        }
        
        function crearCorazones() {
            for (let i = 0; i < 20; i++) {
                const corazon = document.createElement('div');
                corazon.className = 'corazon';
                corazon.innerHTML = '❤️';
                corazon.style.left = Math.random() * 100 + 'vw';
                corazon.style.animationDelay = Math.random() * 5 + 's';
                corazon.style.fontSize = (Math.random() * 2 + 1) + 'rem';
                document.body.appendChild(corazon);
                
                // Eliminar después de la animación
                setTimeout(() => {
                    corazon.remove();
                }, 6000);
            }
        }
        
        function crearConfeti() {
            for (let i = 0; i < 50; i++) {
                const confeti = document.createElement('div');
                confeti.className = 'confeti';
                confeti.style.left = Math.random() * 100 + 'vw';
                confeti.style.animationDelay = Math.random() * 3 + 's';
                confeti.style.width = (Math.random() * 10 + 5) + 'px';
                confeti.style.height = (Math.random() * 10 + 5) + 'px';
                document.body.appendChild(confeti);
                
                // Eliminar después de la animación
                setTimeout(() => {
                    confeti.remove();
                }, 5000);
            }
        }
        
        // Volver a crear confeti periódicamente
        setInterval(crearConfeti, 2000);
    </script>
</body>
</html>
