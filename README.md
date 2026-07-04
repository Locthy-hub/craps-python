# 🎲 Craps — Cassino em Python

Jogo de dados **Craps** desenvolvido em Python puro, rodando direto no terminal. Conta com interface colorida, animações de rolagem, sistema de apostas e estatísticas do jogador.

---

##  Preview

```
╔══════════════════════════════════════════════╗
║       🎲  C R A P S  —  Cassino Python  🎲   ║
╚══════════════════════════════════════════════╝

  🎲 🎲 🎲 .
  ⚂  ⚃  →  7

✔  Você GANHOU! +R$50.00  →  Saldo: R$550.00
```

---

##  Como rodar

Pré-requisitos: apenas **Python 3.10+** (nenhuma dependência externa).

```bash
git clone https://github.com/SEU_USUARIO/craps-python.git
cd craps-python
python jogos_craps.py
```

---

## 📜 Regras do jogo

### Fase Come-Out (primeiro rolar)

| Resultado | Pass Line | Don't Pass |
|---|---|---|
| 7 ou 11 | ✅ Ganha | ❌ Perde |
| 2, 3 ou 12 | ❌ Perde | ✅ Ganha |
| 4, 5, 6, 8, 9 ou 10 | 📍 Define o **Point** | 📍 Define o **Point** |

### Fase Point (após o point ser definido)

| Resultado | Pass Line | Don't Pass |
|---|---|---|
| Repete o Point | ✅ Ganha | ❌ Perde |
| Tira 7 (*seven-out*) | ❌ Perde | ✅ Ganha |
| Qualquer outro número | ⏳ Continua rolando | ⏳ Continua rolando |

**Pagamento:** Pass Line e Don't Pass pagam **1:1** (o lucro é igual ao valor apostado).

---

##  Estrutura do código

| Classe | Ícone | Responsabilidade |
|---|---|---|
| `Dice` | ⚄ | Rola os dados e exibe os emojis |
| `Bet` | 💰 | Guarda tipo e valor da aposta, calcula o payout |
| `Player` | 👤 | Saldo, histórico e apostas do jogador |
| `CrapsGame` | 🧠 | Toda a lógica e regras do jogo — sem nenhum `print()` |
| `Terminal` | 🖥️ | Cores, animações e inputs do terminal |
| `CrapsController` | 🎮 | Orquestra menus, rodadas e o fluxo completo do jogo |

O projeto segue uma separação clara entre **lógica** (`CrapsGame`) e **apresentação** (`Terminal`) — a engine do jogo não sabe nada sobre `print()`, e o terminal não sabe nada sobre as regras.

---

## 📚 Conceitos de POO utilizados

- **Enum** — constantes nomeadas para fases (`GamePhase`) e resultados (`RollResult`)
- **`@property`** — expõe `total` dos dados como atributo, não como método
- **`@staticmethod`** — métodos utilitários de `Terminal` que não dependem de instância
- **Composição** — `Player` possui uma `Bet`; `CrapsGame` possui um `Dice`
- **Encapsulamento** — regras e interface são independentes entre si
- **Type hints** — `-> int`, `Bet | None`, entre outros, para clareza e segurança
- **SRP (Single Responsibility Principle)** — cada classe tem uma única responsabilidade

---

## Tecnologias usadas

- **Python 3** (biblioteca padrão apenas: `random`, `time`, `os`, `enum`, `itertools`)
- Sem dependências externas — roda em qualquer ambiente com Python instalado

---

##  Licença 

Projeto livre para fins de estudo e prática de Programação Orientada a Objetos.
