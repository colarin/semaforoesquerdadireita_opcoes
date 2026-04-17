# 🚦 Controle de LEDs via Serial (Arduino)

Este projeto em Arduino permite controlar dois conjuntos de LEDs (lado esquerdo e direito) através de comandos enviados pela comunicação serial.

## 📌 Descrição

O sistema utiliza quatro LEDs:

- Verde esquerdo
- Vermelho esquerdo
- Verde direito
- Vermelho direito

Através do monitor serial, é possível enviar comandos para ativar sequências específicas de LEDs simulando, por exemplo, um sistema simples de sinalização.

## ⚙️ Funcionamento

O Arduino aguarda comandos via serial. Dependendo do caractere recebido, ele executa uma sequência:

- **'E' ou 'e'** → Controla os LEDs da esquerda  
- **'D' ou 'd'** → Controla os LEDs da direita  

### Sequência executada

Para o lado selecionado:

1. Liga o LED vermelho por 5 segundos  
2. Desliga o LED vermelho  
3. Liga o LED verde por 5 segundos  
4. Desliga o LED verde  

## 🧠 Lógica do Código

- A comunicação serial é iniciada com `Serial.begin(9600)`
- O programa verifica constantemente se há dados disponíveis
- Ao receber um caractere, ele compara com os comandos definidos
- Executa a sequência correspondente usando `digitalWrite()` e `delay()`

## 🔌 Pinagem

| LED                  | Pino |
|----------------------|------|
| Verde Esquerda       | 13   |
| Vermelho Esquerda    | 12   |
| Verde Direita        | 11   |
| Vermelho Direita     | 10   |

## 🛠️ Requisitos

- Arduino (Uno, Nano, etc.)
- 4 LEDs
- 4 resistores (220Ω recomendados)
- Jumpers
- Protoboard
- Arduino IDE

## ▶️ Como usar

1. Monte o circuito conforme a pinagem  
2. Faça upload do código para o Arduino  
3. Abra o **Monitor Serial**  
4. Configure para **9600 baud**  
5. Envie:
   - `E` para controlar o lado esquerdo  
   - `D` para controlar o lado direito  

## 💡 Possíveis melhorias

- Substituir `delay()` por `millis()` para tornar o sistema não bloqueante  
- Adicionar mais comandos (ex: ligar ambos os lados)  
- Criar interface com botões físicos  
- Integrar com Bluetooth ou Wi-Fi  

## 📄 Licença

Este projeto é de uso livre para fins educacionais.

👨‍💻 Autor

Projeto desenvolvido por Wagner 🚀
