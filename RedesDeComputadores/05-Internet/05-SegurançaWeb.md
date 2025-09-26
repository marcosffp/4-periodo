# 📌 Resumo Didático: Segurança na Web

## **1. Introdução à Segurança da Informação**
- **Definição:** A informação é um ativo valioso que precisa ser protegido contra acessos não autorizados, alterações indevidas e ataques. Deve estar disponível para entidades autorizadas quando necessário.
- **Riscos em Redes:** Dados em redes podem ser espionados, copiados ou alterados por terceiros, expondo informações sensíveis.

---

## **2. Serviços Essenciais de Segurança**
1. **Sigilo (Confidencialidade):** Proteção contra acessos não autorizados.
2. **Autenticação:** Garantia de que transmissor e receptor são quem dizem ser.
3. **Não Repúdio:** O emissor não pode negar que enviou uma mensagem.
4. **Integridade:** Garantia de que os dados não foram alterados durante a transmissão.
5. **Disponibilidade:** Garantia de que dados e serviços estarão acessíveis para usuários autorizados.

---

## **3. Tipos de Ataques**
### **Ataques Passivos:**
- **Espionagem:** Monitoramento de transmissões para obter informações.
- **Análise de Tráfego:** Identificação de padrões e origens de dados.
- **Características:** Difíceis de detectar; foco na prevenção.

### **Ataques Ativos:**
- **Modificação:** Alteração de dados ou sua ordem.
- **Falsificação:** Entidade se passando por outra.
- **Repetição:** Captura e retransmissão de dados.
- **Negação de Serviço (DoS):** Interrupção de serviços.
- **Características:** Fáceis de detectar; foco na detecção e recuperação.

---

## **4. Segurança em Camadas de Rede**
### **Camada Física:**
- Proteção de cabos e conexões físicas.
- Uso de sensores e salas cofre.

### **Camada de Enlace:**
- Criptografia de quadros.
- Bloqueio por endereço MAC.
- Segmentação com VLANs.

### **Camada de Rede:**
- Filtros de pacotes.
- Uso de IPSec.

### **Camada de Transporte:**
- Bloqueio de portas.
- Criptografia processo a processo.

### **Camada de Aplicação:**
- Autenticação de usuários.
- Criptografia de dados.

---

## **5. Criptografia: A Base da Segurança**
- **Definição:** Transformação matemática de mensagens para torná-las ininteligíveis sem a chave correta.
- **Elementos:**
  - **Texto Claro:** Mensagem original.
  - **Texto Cifrado:** Mensagem criptografada.
  - **Chave:** Número usado para cifrar e decifrar mensagens.
- **Tipos de Algoritmos:**
  1. **Chave Simétrica:** Mesma chave para cifrar e decifrar (ex.: DES, AES).
  2. **Chave Assimétrica:** Chaves pública e privada distintas (ex.: RSA).
  3. **Funções de Hash:** Geração de resumos de mensagens (ex.: MD5, SHA-1).

---

## **6. Aplicações de Criptografia**
1. **Sigilo:** Proteção de dados com chaves simétricas ou assimétricas.
2. **Autenticação:** Uso de chaves assimétricas para garantir a identidade do emissor.
3. **Não Repúdio:** Garantia de autenticidade com entidades confiáveis.
4. **Integridade:** Verificação de alterações com funções de hash.
5. **Assinatura Digital:** Combinação de hash e criptografia para autenticar mensagens.
6. **Certificados Digitais:** Vinculação de chaves públicas a entidades por Autoridades Certificadoras (AC).

---

## **7. Protocolos de Segurança**
### **SSL/TLS (Secure Socket Layer/Transport Layer Security):**
- **Função:** Criação de conexões seguras entre cliente e servidor.
- **Características:**
  - Negociação de parâmetros de segurança.
  - Autenticação mútua.
  - Criptografia de dados.
  - Proteção de integridade.
- **Exemplo:** HTTPS (HTTP sobre SSL/TLS).

### **VPN (Virtual Private Network):**
- **Definição:** Rede privada virtual que utiliza criptografia para proteger dados transmitidos em redes públicas.
- **Características:**
  - Tunelamento para privacidade.
  - Autenticação de usuários.
  - Criptografia de dados.

---

## **8. Firewalls**
- **Definição:** Componentes que protegem redes locais contra ataques externos.
- **Tipos:**
  1. **Filtro de Pacotes:** Roteamento seletivo com base em regras.
  2. **Gateway de Aplicação (Proxy):** Controle de tráfego na camada de aplicação.
- **Vantagens:** Controle de acesso, auditoria e proteção contra tráfego malicioso.

---

## **9. Boas Práticas de Segurança**
1. **Senhas Fortes:** Combinação de caracteres variados, trocas periódicas.
2. **Atualizações:** Aplicação de patches em sistemas e softwares.
3. **Controle de Acesso:** Restrição de acessos físicos e lógicos.
4. **Backups:** Políticas regulares de backup e restauração.
5. **Educação de Usuários:** Treinamentos sobre segurança da informação.
6. **Monitoramento:** Ativação de logs e auditorias regulares.

---

## **10. Referências**
- **CERT.br:** Segurança de Redes de Computadores.
- **Forouzan, B. A.:** Comunicação de Dados e Redes de Computadores.
- **Tanenbaum, A. S.:** Redes de Computadores.
- **McClure, S.:** Hackers Expostos.

---

## **📌 Conclusão**
A segurança na web é um processo contínuo que envolve a proteção de dados, autenticação de entidades e prevenção de ataques. A implementação de criptografia, firewalls, VPNs e boas práticas de segurança são essenciais para garantir a integridade e confidencialidade das informações em redes de computadores.