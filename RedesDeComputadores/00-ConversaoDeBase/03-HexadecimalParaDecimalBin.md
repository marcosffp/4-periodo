# 🔢 **Conversão de Hexadecimal para Decimal e Binário**

Aprenda agora como converter números hexadecimais para decimal e binário de forma prática e eficiente!

## **1️⃣ Hexadecimal → Decimal**
Cada dígito hexadecimal representa uma potência de 16. A conversão é feita multiplicando cada dígito por 16 elevado à sua posição (começando em 0 da direita para esquerda).

### **Método: Soma das Potências de 16**
✅ **Passo a Passo (Exemplo: `FADA` → Decimal)**

| Dígito | Valor Decimal | Posição (n) | Cálculo (Valor × 16ⁿ) |
|--------|---------------|-------------|-----------------------|
| F      | 15            | 3           | 15 × 16³ = 15 × 4096 = **61440** |
| A      | 10            | 2           | 10 × 16² = 10 × 256 = **2560** |
| D      | 13            | 1           | 13 × 16¹ = 13 × 16 = **208** |
| A      | 10            | 0           | 10 × 16⁰ = 10 × 1 = **10** |

**Soma dos valores:**
61440 + 2560 + 208 + 10 = **64218**

➡️ `FADA` em hexadecimal = `64218` em decimal ✅

## **2️⃣ Hexadecimal → Binário**
Cada dígito hexadecimal corresponde exatamente a 4 bits (nibble). Basta converter cada dígito separadamente.

### **Método: Conversão Dígito a Dígito**
✅ **Passo a Passo (Exemplo: `FADA` → Binário)**

| Dígito | Valor Binário (4 bits) |
|--------|------------------------|
| F      | 1111 (8+4+2+1)         |
| A      | 1010 (8+0+2+0)         |
| D      | 1101 (8+4+0+1)         |
| A      | 1010 (8+0+2+0)         |

**Juntando tudo:**
`F` `A` `D` `A` → `1111` `1010` `1101` `1010`

➡️ `FADA` em hexadecimal = `1111101011011010` em binário ✅
