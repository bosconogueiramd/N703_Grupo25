
# Sistema de Treinamento em Regulação Médica - Visita Guiada e Sistema de Validação de Certificados - RegulaCert

## 📌 Definição de Arquitetura
O projeto é composto por dois sistemas distintos que interagem entre si através de um sistema de mensageria assíncrona baseado em RabbitMQ:

### **Sistema Visita Guiada**
- Frontend: HTML, CSS, JavaScript, Bootstrap
- Backend: Django (Python)
- Banco de Dados: MySQL

### **Sistema RegulaCert**
- Frontend: React.js
- Backend: Node.js
- Banco de Dados: MySQL

### **Comunicação e Integração**
- A comunicação entre o sistema Visita Guiada e o sistema RegulaCert ocorre por meio de RabbitMQ, utilizando o protocolo AMQP para mensagens assíncronas.
- O backend do sistema Visita Guiada publica eventos no RabbitMQ.
- O backend do sistema RegulaCert consome eventos do RabbitMQ e valida os dados recebidos com base no banco de dados.

### **Docker**
- Ambos os sistemas são conteinerizados com Docker, garantindo isolamento e escalabilidade.

---

## 🖥️ Como Rodar o Projeto Localmente:

### **1. Clonar o Repositório**
```bash
git clone https://github.com/bosconogueiramd/N703_Grupo25.git
```

### **2. Acessar o Diretório do Projeto**
```bash
cd N703_Grupo25
```

### **3. Configurar o Ambiente Docker**
- Subir os contêineres com Docker Compose:
```bash
docker-compose up --build
```

### **4. Acessar o Sistema**
- **Sistema Visita Guiada:**
[http://localhost:8000](http://localhost:8000)

- **Sistema RegulaCert:**
[http://localhost:3000](http://localhost:3000)

### **5. Para Parar o Sistema**
```bash
docker-compose down
```

---

## 🛠️ Tecnologias utilizadas
- Django (Python)
- Node.js
- React.js
- RabbitMQ
- Docker
- MySQL
