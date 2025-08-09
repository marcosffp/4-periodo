# Conversão de Números Decimais para Binário e Hexadecimal  

Este guia explica passo a passo como converter números decimais para **binário** (base 2) e **hexadecimal** (base 16), utilizando métodos didáticos e exemplos práticos.  

---  

## 🔢 **Conversão de Decimal para Binário**  

O sistema binário representa números usando apenas **0** e **1**. A conversão pode ser feita por **subtrações sucessivas** de potências de 2 ou por **divisões sucessivas** por 2.  

### **Método 1: Subtrações Sucessivas**  

1️⃣ **Liste as potências de 2 em ordem decrescente:**  
   ```
   128, 64, 32, 16, 8, 4, 2, 1
   ```  

2️⃣ **Escolha um número decimal (exemplo: 210).**  

3️⃣ **Subtraia a maior potência de 2 possível e marque "1" se couber, "0" caso contrário:**  

| Potência de 2 | Subtração | Bit |
|--------------|-----------|-----|
| 128          | 210 - 128 = 82 | 1 |
| 64           | 82 - 64 = 18   | 1 |
| 32           | 18 - 32 → Não cabe | 0 |
| 16           | 18 - 16 = 2    | 1 |
| 8            | 2 - 8 → Não cabe  | 0 |
| 4            | 2 - 4 → Não cabe  | 0 |
| 2            | 2 - 2 = 0       | 1 |
| 1            | 0 - 1 → Não cabe  | 0 |

4️⃣ **Resultado:**  
   - Junte os bits na ordem: **11010010**  
   - **210 em decimal = 11010010 em binário** ✅  

---  

### **Método 2: Divisões Sucessivas**  

1️⃣ **Divida o número por 2 e anote o resto.**  
2️⃣ **Repita até o quociente ser 0.**  
3️⃣ **Leia os restos de baixo para cima.**  

**Exemplo (210):**  

| Divisão | Quociente | Resto |
|---------|-----------|-------|
| 210 ÷ 2 | 105       | 0     |
| 105 ÷ 2 | 52        | 1     |
| 52 ÷ 2  | 26        | 0     |
| 26 ÷ 2  | 13        | 0     |
| 13 ÷ 2  | 6         | 1     |
| 6 ÷ 2   | 3         | 0     |
| 3 ÷ 2   | 1         | 1     |
| 1 ÷ 2   | 0         | 1     |

- Restos lidos de baixo para cima: **11010010** (mesmo resultado).  

---  

## 🔠 **Conversão de Decimal para Hexadecimal**  

O sistema hexadecimal usa 16 símbolos: **0-9** e **A-F** (onde A=10, B=11, ..., F=15).  

### **Método: Divisões Sucessivas por 16**  

1️⃣ **Divida o número por 16 e anote o resto.**  
2️⃣ **Converta restos ≥10 em letras (A-F).**  
3️⃣ **Leia de baixo para cima.**  

**Exemplo (16848123):**  

| Divisão       | Quociente | Resto | Hexadecimal |
|---------------|-----------|-------|-------------|
| 16848123 ÷ 16 | 1053007   | 11    | B           |
| 1053007 ÷ 16  | 65812     | 15    | F           |
| 65812 ÷ 16    | 4113      | 4     | 4           |
| 4113 ÷ 16     | 257       | 1     | 1           |
| 257 ÷ 16      | 16        | 1     | 1           |
| 16 ÷ 16       | 1         | 0     | 0           |
| 1 ÷ 16        | 0         | 1     | 1           |

- Restos lidos de baixo para cima: **10114FB**  
- **16848123 em decimal = 10114FB em hexadecimal** ✅  

---  

