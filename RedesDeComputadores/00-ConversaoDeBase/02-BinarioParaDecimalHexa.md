# 🔢 **Conversão de Binário para Decimal e Hexadecimal**  

Este guia ensina como converter números **binários (base 2)** para **decimal (base 10)** e **hexadecimal (base 16)** de forma simples e prática.  

---  

## **1️⃣ Binário → Decimal**  
Cada bit em um número binário representa uma potência de 2. Quanto mais à **esquerda**, maior o valor.  

### **Método: Soma das Potências de 2**  
✅ **Passo a Passo (Exemplo: `11010010` → Decimal)**  

| Bit (Posição) | Valor (2ⁿ) | Cálculo |
|--------------|------------|---------|
| **1** (7ª posição) | 128 (2⁷) | 1 × 128 = **128** |
| **1** (6ª posição) | 64 (2⁶)  | 1 × 64 = **64** |
| **0** (5ª posição) | 32 (2⁵)  | 0 × 32 = **0** |
| **1** (4ª posição) | 16 (2⁴)  | 1 × 16 = **16** |
| **0** (3ª posição) | 8 (2³)   | 0 × 8 = **0** |
| **0** (2ª posição) | 4 (2²)   | 0 × 4 = **0** |
| **1** (1ª posição) | 2 (2¹)   | 1 × 2 = **2** |
| **0** (0ª posição) | 1 (2⁰)   | 0 × 1 = **0** |

**Some todos os valores:**  
128 + 64 + 0 + 16 + 0 + 0 + 2 + 0 = **210**  

➡️ **`11010010` em binário = `210` em decimal** ✅  

---  

## **2️⃣ Binário → Hexadecimal**  
Hexadecimal agrupa **4 bits** em **1 dígito hex** (0-9, A-F).  

### **Método: Agrupar em Blocos de 4 Bits**  
✅ **Passo a Passo (Exemplo: `11010010` → Hexadecimal)**  

1️⃣ **Divida em blocos de 4 bits (da direita para esquerda):**  
   - Se faltarem bits, complete com **zeros à esquerda**.  
   - `11010010` → `1101` `0010`  

2️⃣ **Converta cada bloco para hexadecimal:**  

| Bloco | Cálculo (Potências de 2) | Valor Decimal | Hexadecimal |
|-------|--------------------------|---------------|-------------|
| **1101** | (1×8) + (1×4) + (0×2) + (1×1) = **13** | 13 | **D** |
| **0010** | (0×8) + (0×4) + (1×2) + (0×1) = **2** | 2 | **2** |

3️⃣ **Junte os resultados:**  
   - `1101` = **D**  
   - `0010` = **2**  

➡️ **`11010010` em binário = `D2` em hexadecimal** ✅  

---  

## **📌 Tabela de Referência Rápida**  

### **Binário → Hexadecimal (4 bits)**  
| Binário | Hexadecimal |
|---------|-------------|
| 0000    | 0           |
| 0001    | 1           |
| 0010    | 2           |
| ...     | ...         |
| 1001    | 9           |
| 1010    | A           |
| 1011    | B           |
| 1100    | C           |
| 1101    | D           |
| 1110    | E           |
| 1111    | F           |

---  