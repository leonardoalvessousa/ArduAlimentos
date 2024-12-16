
![BannerArdualimentos](https://raw.githubusercontent.com/leonardoalvessousa/ArduAlimentos/refs/heads/main/BannerProj.jpg)

## Resumo da Prática

Neste projeto, você aprenderá a integrar um Arduino Uno com um sensor de umidade do solo resistivo na plataforma **[TINKERCAD](https://www.tinkercad.com/)**. Ao ajustar a umidade detectada pelo sensor no simulador, o brilho de um LED conectado ao Arduino irá variar de acordo com os níveis de umidade do solo.

> [!NOTE]
> Este projeto foi desenvolvido para um minicurso ministrado no evento da II Semana de Engenharia de Alimentos da Unilab na qual fui ministrador

### Materiais Necessários

- Arduino Uno
- Sensor de Umidade do Solo (Resistivo)
- Resistor de 10k ohms
- Jumper wires
- Protoboard (opcional) 
- **[Simulador Tinkercad/LOGIN](https://www.tinkercad.com/login)**

### Ligações no Arduino Uno

![Texto Alternativo](https://raw.githubusercontent.com/leonardoalvessousa/ArduAlimentos/refs/heads/main/CircuiteArdu.jpg)

### Código Arduino

```ArduinoCode
// C++ code

int led = 11;

int pinSensor = A0;
int umidade;

void setup()
{
  pinMode(led, OUTPUT);
  pinMode(pinSensor, INPUT);
}

void loop()
{
  umidade = analogRead(pinSensor);
  
  map(umidade,0,1023,0,100);
  
  analogWrite(led, umidade);
}
```

**Definindo as variáveis:**

- **`int led = 11;`**: Essa linha define uma variável chamada `led` e atribui o valor `11` a ela. `11` representa o número do pino do Arduino que você vai usar para controlar um LED.
- **`int pinSensor = A0;`**: Define uma variável chamada `pinSensor` e atribui o valor `A0` a ela. `A0` representa o número do pino analógico do Arduino que você vai usar para conectar o sensor de umidade.
- **`int umidade;`**: Define uma variável chamada `umidade` para armazenar a leitura do sensor. 

**Configurando o Arduino:**

- **`void setup()`**: Essa função é executada apenas uma vez quando o Arduino é ligado. Aqui, você configura os pinos:
    - **`pinMode(led, OUTPUT);`**: Define o pino do LED como uma saída, ou seja, o Arduino irá enviar sinais para o LED.
    - **`pinMode(pinSensor, INPUT);`**: Define o pino do sensor como uma entrada, ou seja, o Arduino irá receber sinais do sensor.

**Lendo e processando os dados:**

- **`void loop()`**: Essa função é executada repetidamente, em um loop infinito.
    - **`umidade = analogRead(pinSensor);`**: Lê o valor analógico do sensor de umidade e armazena na variável `umidade`. O sensor de umidade fornece um valor entre 0 e 1023, que representa a umidade do solo.
    - **`map(umidade,0,1023,0,100);`**: Essa linha ajusta o valor da `umidade` para uma escala mais fácil de entender. Ela converte o valor original (0-1023) para uma escala de 0 a 100, onde 0 representa a menor umidade e 100 a maior umidade.
    - **`analogWrite(led, umidade);`**: Essa linha controla o brilho do LED de acordo com a umidade. O valor da `umidade`, que agora está em uma escala de 0 a 100, é usado para definir o brilho do LED. Um valor de 0 significa que o LED estará apagado, e um valor de 100 significa que o LED estará no brilho máximo.

### Resultados da Simulação

![Texto Alternativo](https://raw.githubusercontent.com/leonardoalvessousa/ArduAlimentos/refs/heads/main/ardugiflogo.gif)


## 😼 Autor

🐈‍⬛ @leonardoalvessousa

## 🎁 Expressões de gratidão

- Conte a outras pessoas sobre este projeto 📢;
- Pague uma cerveja para o autor **[🍺](https://nubank.com.br/cobrar/f7g6w/6755dd2c-8e3d-4c14-9976-b1afefc8ae07)**;

