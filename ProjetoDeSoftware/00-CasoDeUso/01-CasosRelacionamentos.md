# 📚 **Resumo Didático sobre Casos de Uso**

## **1️⃣ O que são Casos de Uso?**
Casos de uso são **documentos textuais** que especificam requisitos funcionais de um sistema, descrevendo **como os atores interagem** com o sistema para alcançar um objetivo específico. Eles são criados na fase de **Especificação de Requisitos**, especialmente em processos do tipo **Waterfall**.

### **Características Principais:**
✔ **Foco no usuário:** Descrevem a perspectiva de um **ator** (humano, sistema ou hardware) que interage com o sistema.  
✔ **Requisitos funcionais:** Representam **o que** o sistema deve fazer, sem detalhar implementação.  
✔ **Base para desenvolvimento:** Direcionam atividades posteriores no ciclo de vida do software.  

---

## **2️⃣ Componentes do Modelo de Casos de Uso (MCU)**
O MCU possui **duas partes**:
1. **Descrição textual** (fluxo de interações).  
2. **Diagrama gráfico** (visão visual usando UML).  

### **Elementos Principais:**
| Elemento          | Descrição                                                                 | Exemplo (Imagem)                     |
|-------------------|---------------------------------------------------------------------------|---------------------------------------|
| **Ator**          | Entidade externa que interage com o sistema (usuário, sistema, hardware). | `Usuário`, `Professor`, `Cliente`.    |
| **Caso de Uso**   | Funcionalidade do sistema (objetivo específico).                          | `Reservar Livro`, `Realizar Pagamento`. |
| **Relacionamentos**| Conexões entre atores e casos de uso (associação, inclusão, extensão).  | `<<include>>`, `<<extend>>`.          |

---

## **3️⃣ Tipos de Relacionamentos**
| Tipo             | Símbolo         | Descrição                                                                 | Exemplo (Imagem)                          |
|------------------|-----------------|---------------------------------------------------------------------------|--------------------------------------------|
| **Comunicação**  | Linha simples   | Ator interage com um caso de uso.                                         | `Cliente` ↔ `Realizar Saque`.              |
| **Inclusão**     | `<<include>>`   | Um caso de uso **sempre** executa outro.                                  | `Realizar Saque` ➔ `Validar Senha`.        |
| **Extensão**     | `<<extend>>`    | Um caso de uso **opcionalmente** estende outro.                           | `Pagamento` ➔ `Aplicar Desconto`.          |
| **Generalização**| Seta oca        | Herança (um caso de uso ou ator é especialização de outro).               | `Professor` ➞ `Usuário`.                   |

---

## **4️⃣ Como Identificar Elementos?**
- **Atores:**  
  - *"Quem usa o sistema?"* (Ex: `Cliente`, `Sistema de Pagamento`).  
  - *"Quem recebe notificações?"* (Ex: `Administrador`).  

- **Casos de Uso:**  
  - *"Quais objetivos o sistema deve cumprir?"* (Ex: `Reservar Livro`, `Emitir Extrato`).  

- **Relacionamentos:**  
  - *"Essa funcionalidade depende de outra?"* → `<<include>>`.  
  - *"Há comportamentos opcionais?"* → `<<extend>>`.  

---

## **5️⃣ Exemplo Prático (Baseado na Imagem)**
### **Cenário: Sistema de Biblioteca**
| Elemento          | Exemplo               | Relacionamento              |
|-------------------|-----------------------|-----------------------------|
| **Atores**        | `Usuário`, `Professor`| Comunicação com `Reservar Livro`. |
| **Casos de Uso**  | `Reservar Livro`      | `<<include>> Validar Cadastro`. |
|                   | `Solicitar Compra`    | `<<extend>> Aprovar Orçamento`. |

**Diagrama Simplificado:**
```
Usuário → (Reservar Livro) <<include>> (Validar Cadastro)
Professor → (Solicitar Compra) <<extend>> (Aprovar Orçamento)
```

---
