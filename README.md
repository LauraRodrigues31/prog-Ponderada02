# Ponderada de programação

## Laura de Araujo Rodrigues

Você começou a estagiar no Departamento de Engenharia de Trânsito e ficou responsável por controlar o fluxo em uma via movimentada do bairro Butantã. Seu desafio é montar e programar um semáforo que garanta a segurança de pedestres e veículos, seguindo a lógica de tempo de cada fase das luzes, desde a montagem dos LEDs até a programação da sequência correta. Agora, você tem a chance de aplicar seus conhecimentos e desenvolver um sistema essencial para o controle do trânsito. Será que você consegue criar um semáforo que funcione perfeitamente, como aqueles que encontramos nas ruas todos os dias?

### Parte 1: Montagem Física do Semáforo


https://github.com/user-attachments/assets/52bb091c-f998-487f-b106-70539c82c6e3



### Parte 2: Programação e Lógica do Semáforo
```cpp
// Definindo constantes para os pinos dos LEDs dos semáforos e pedestres
const int semaforoVerde = 2;       // Pino do LED verde do semáforo
const int semaforoAmarelo = 4;     // Pino do LED amarelo do semáforo
const int semaforoVermelho = 7;    // Pino do LED vermelho do semáforo
const int pedestreVermelho = 12;   // Pino do LED vermelho do pedestre
const int pedestreVerde = 8;       // Pino do LED verde do pedestre

void setup() {
  // Configurando os pinos como saídas
  pinMode(semaforoVerde, OUTPUT);
  pinMode(semaforoAmarelo, OUTPUT);
  pinMode(semaforoVermelho, OUTPUT);
  pinMode(pedestreVermelho, OUTPUT);
  pinMode(pedestreVerde, OUTPUT);

  // Inicialmente, todos os LEDs são apagados
  apagarTodos();
}

void loop() {
  // Sequência de estados do semáforo e do pedestre
  estadoVermelho();  // Semáforo vermelho e pedestre verde
  estadoAmarelo();   // Semáforo amarelo e pedestre ainda verde
  estadoVerde();     // Semáforo verde e pedestre vermelho
}

void apagarTodos() {
  // Função para apagar todos os LEDs
  digitalWrite(semaforoVerde, LOW);
  digitalWrite(semaforoAmarelo, LOW);
  digitalWrite(semaforoVermelho, LOW);
  digitalWrite(pedestreVermelho, LOW);
  digitalWrite(pedestreVerde, LOW);
}

void estadoVermelho() {
  // Configuração do estado onde o semáforo está vermelho e o pedestre pode atravessar
  apagarTodos(); // Apaga todos os LEDs para garantir um estado inicial
  digitalWrite(semaforoVermelho, HIGH);  // Liga o LED vermelho do semáforo
  digitalWrite(pedestreVerde, HIGH);     // Liga o LED verde do pedestre
  delay(6000); // Mantém esse estado por 6 segundos
}

void estadoAmarelo() {
  // Configuração do estado onde o semáforo está amarelo e o pedestre ainda pode atravessar
  apagarTodos(); // Apaga todos os LEDs para garantir um estado inicial
  digitalWrite(semaforoAmarelo, HIGH);   // Liga o LED amarelo do semáforo
  digitalWrite(pedestreVerde, HIGH);     // Mantém o LED verde do pedestre ligado
  delay(2000); // Mantém esse estado por 2 segundos
}

void estadoVerde() {
  // Configuração do estado onde o semáforo está verde e o pedestre deve aguardar
  apagarTodos(); // Apaga todos os LEDs para garantir um estado inicial
  digitalWrite(semaforoVerde, HIGH);     // Liga o LED verde do semáforo
  digitalWrite(pedestreVermelho, HIGH);  // Liga o LED vermelho do pedestre
  delay(2000); // Mantém esse estado por 2 segundos
}

```

### Parte 3: Avaliação de Pares

### Tabela de Avaliação entre Pares

#### Laura Rodrigues

|Critério|	Contempla (Pontos)|	Contempla Parcialmente (Pontos)	|Não Contempla (Pontos)	|Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores	|3	|	| | |	
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo	|3	|	| | |	
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |3 | |	 | |	
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código | 2,8|	 |	 | |	
| | | | |Pontuação Total|

#### Lucas Guerra
|Critério|	Contempla (Pontos)|	Contempla Parcialmente (Pontos)	|Não Contempla (Pontos)	|Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores	|3|	| | |	
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo	|3	|	| | |	
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | 3|	 |	| |	
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |	2,8 |	 |	 | |	
| | | | |Pontuação Total|
