[README.md](https://github.com/user-attachments/files/32262880/README.md)
# Avatar — Mestres da Dobra

Projeto de POO em Java com interface gráfica Swing, originalmente temático de Naruto/Bijū e agora totalmente retematizado para **Avatar: A Lenda de Aang**.

## Tema

O jogador explora diferentes regiões do mundo de Avatar, encontra dobradores, enfrenta-os em combates por turnos e tenta convencê-los a entrar para sua equipe.

### Mapeamento de conceitos

| Conceito do jogo | Tema Avatar |
|---|---|
| Criatura/personagem | `Dobrador` |
| Tipo elemental | `TipoDobra` |
| Fogo | 🔥 FOGO |
| Água | 💧 ÁGUA |
| Terra | 🪨 TERRA |
| Ar | 🌪️ AR |
| Treinador | `Mestre` |
| Captura | `Recrutamento` |
| Pokédex/registro | `RegistroDobradores` |
| Centro de cura | Templo de Cura |
| Batalha | Confronto entre dobradores |

## Personagens

O projeto utiliza dobradores conhecidos do universo de Avatar:

- Aang — Ar
- Jinora — Ar
- Katara — Água
- Mestre Pakku — Água
- Toph — Terra
- Rei Bumi — Terra
- Zuko — Fogo
- Azula — Fogo
- Iroh — Fogo
- Avatar Roku — Fogo

## Estrutura

```text
src/
├── JogoGUI.java
├── gui/
│   ├── CarregadorImagem.java
│   ├── Regiao.java
│   ├── TelaEncontro.java
│   └── TelaMapa.java
├── modelo/
│   ├── Dobrador.java
│   ├── DobradorAgua.java
│   ├── DobradorAr.java
│   ├── DobradorFogo.java
│   ├── DobradorTerra.java
│   └── personagens/
│       (Aang, Katara, Toph, Zuko, Azula, Iroh, Roku, Pakku, Bumi e Jinora)
├── sistema/
│   ├── Batalha.java
│   ├── Mestre.java
│   ├── Recrutamento.java
│   └── RegistroDobradores.java
├── tipos/
│   └── TipoDobra.java
└── testes/
    └── testes JUnit
```

## Mecânicas

1. Escolha um dobrador inicial.
2. Explore seis regiões do mundo de Avatar.
3. Encontre dobradores diferentes.
4. Use as dobras em confrontos por turnos.
5. Reduza a vida do adversário para aumentar a chance de recrutamento.
6. Recrute dobradores e monte uma equipe de até 6 integrantes.
7. Use o Templo de Cura para recuperar a equipe.
8. Consulte o Registro de Dobradores para acompanhar quem já foi encontrado.

## Vantagem elemental

A regra de vantagem fica centralizada em `TipoDobra.multiplicador()`, mantendo a lógica de combate independente das classes de personagens.

```text
🔥 FOGO  → vantagem contra → 🌪️ AR
🌪️ AR    → vantagem contra → 💧 ÁGUA
💧 ÁGUA  → vantagem contra → 🔥 FOGO
🪨 TERRA → vantagem contra → 💧 ÁGUA
```

A classe `Dobrador` calcula o dano e as subclasses/personagens fornecem habilidades especiais por polimorfismo.

## Polimorfismo

Cada personagem implementa sua própria habilidade por meio de:

- `bonusEspecial(Dobrador alvo)`
- `efeitoPosAtaque(Dobrador alvo, int dano)`

Exemplos:

- **Katara:** recupera vida ao causar dano.
- **Zuko:** fica mais forte quando sua vida está baixa.
- **Toph:** recebe bônus contra adversários com defesa menor.
- **Azula:** possui bônus de finalização.
- **Aang:** ganha força enquanto mantém a vida alta.
- **Iroh:** combina dano extra com recuperação de vida.

## Como executar

A classe principal da interface gráfica é:

```text
JogoGUI
```

Compile o conteúdo de `src` com Java 17 ou superior e execute `JogoGUI`.

Também existem classes `Teste*.java` para demonstrações rápidas no console e uma pasta de testes JUnit.

## Observação

As imagens incluídas no projeto foram substituídas por artes gráficas originais de identificação dos elementos e personagens, evitando a dependência das antigas imagens temáticas de Naruto.
