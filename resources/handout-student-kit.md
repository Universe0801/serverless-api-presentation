# 🎓 TaskFlow Student Starter Kit

> **Tu kit de supervivencia para comenzar con serverless**  
> *Todo lo que necesitas para ir de cero a deploy en AWS*

## 🚀 Quick Start (Si quieres empezar YA)

```bash
# 1. Clona TaskFlow
git clone https://github.com/universe-org/serverless-api-demo.git
cd serverless-api-demo

# 2. Deploy en 3 comandos
sam build
sam deploy --guided
# Sigue las instrucciones en pantalla

# 3. ¡Felicidades! Ya tienes una API en producción
```

**⏱️ Tiempo total:** 10-15 minutos  
**💰 Costo:** $0.00 con AWS Free Tier  
**🔗 Resultado:** API REST funcionando con URL mundial

---

## ☑️ Setup Completo Paso a Paso

### **1. Crear Cuenta AWS (Free Tier)**
```
🔗 Enlace: https://aws.amazon.com/free/

✅ INCLUYE GRATIS POR 12 MESES:
• 1M requests Lambda por mes
• 25GB DynamoDB storage  
• 1M API Gateway requests por mes
• CloudWatch logs básicos
• Y mucho más...

💳 Necesitas tarjeta de crédito pero NO te cobrarán si te mantienes en Free Tier
⚠️  TIP: Configura billing alerts para estar tranquilo
```

### **2. Instalar Herramientas en tu Laptop**

#### **AWS CLI:**
```bash
# macOS
brew install awscli

# Windows
# Descargar desde: https://aws.amazon.com/cli/

# Linux (Ubuntu/Debian)
sudo apt install awscli

# Verificar instalación
aws --version
# Debe mostrar: aws-cli/2.x.x
```

#### **SAM CLI:**
```bash
# macOS
brew install aws-sam-cli

# Windows
# Descargar desde: https://aws.amazon.com/serverless/sam/

# Linux
# Seguir: https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html

# Verificar instalación  
sam --version
# Debe mostrar: SAM CLI, version 1.x.x
```

#### **Java 21+ (opcional pero recomendado):**
```bash
# macOS
brew install openjdk@21

# Windows
# Descargar desde: https://adoptium.net/

# Linux (Ubuntu)
sudo apt install openjdk-21-jdk

# Verificar
java -version
# Debe incluir: openjdk version "21.x.x"
```

### **3. Configurar AWS CLI**
```bash
# Comando para configurar
aws configure

# Te preguntará:
AWS Access Key ID: [Obtener desde AWS Console > IAM]
AWS Secret Access Key: [Obtener desde AWS Console > IAM] 
Default region: us-east-1
Default output format: json

# Verificar configuración
aws sts get-caller-identity
# Debe mostrar tu User ID y Account
```

**🔐 Cómo obtener las keys:**
1. AWS Console → IAM → Users → [tu-usuario] → Security credentials
2. Create access key → Command Line Interface (CLI)
3. Copiar Access Key ID y Secret Access Key

---

## 💡 Tu Primer Proyecto Serverless

### **Opción 1: Modificar TaskFlow (Fácil)**
```bash
# Ideas para modificar:
• Agregar campo "priority" a las tareas
• Nuevo endpoint GET /tasks/completed
• Cambiar respuestas JSON
• Agregar timestamp automático

# Workflow:
1. Modificar código en src/
2. sam build
3. sam deploy
4. Probar cambios
```

### **Opción 2: Tu Propia API (Intermedio)**
```bash
# Ideas de APIs simples:
📚 Gestión de libros personales
🍳 Recetas de cocina favoritas  
💰 Tracker de gastos estudiantiles
🎵 Playlists colaborativas
🏋️ Log de ejercicios
🎮 Leaderboard de videojuegos

# Usar TaskFlow como template y modificar todo
```

### **Opción 3: Proyecto Original (Avanzado)**
```bash
# Empezar desde cero con SAM
sam init

# Seleccionar:
1. AWS Quick Start Templates
2. Hello World Example
3. Python 3.11 o Java 21
4. Zip (no container)

# Y construir tu idea desde ahí
```

---

## 🧠 Comandos de Supervivencia

### **Comandos SAM Esenciales:**
```bash
# Desarrollo local
sam build                     # Compila tu código
sam local start-api           # Corre API localmente
sam local invoke              # Prueba función específica
sam logs                      # Ve logs de CloudWatch

# Deploy y gestión
sam deploy                    # Deploy a AWS
sam delete                    # Elimina todo el stack
sam list stack-outputs        # Ve URLs y recursos creados

# Debugging
sam logs --name NombreFuncion --tail    # Logs en tiempo real
```

### **AWS CLI Útiles:**
```bash
# Ver tus stacks de CloudFormation
aws cloudformation list-stacks

# Ver costos actuales
aws ce get-cost-and-usage --time-period Start=2024-01-01,End=2024-12-31 --granularity MONTHLY --metrics BlendedCost

# Listar funciones Lambda
aws lambda list-functions

# Ver tablas DynamoDB
aws dynamodb list-tables
```

### **Testing de API:**
```bash
# Con curl
curl -X POST https://tu-api-url.com/endpoint -H "Content-Type: application/json" -d '{"key":"value"}'

# Con httpie (más fácil)
pip install httpie
http POST https://tu-api-url.com/endpoint key=value
```

---

## 🔧 Troubleshooting Común

### **"AccessDenied" Errors:**
```bash
# Problema: Permisos insuficientes
# Solución: Revisar IAM policies

aws iam list-attached-user-policies --user-name tu-username
# Necesitas: PowerUserAccess o similares para desarrollo
```

### **"Stack already exists":**
```bash
# Problema: Intentas crear stack que ya existe
# Solución: Usar nuevo nombre o eliminar existing

sam delete --stack-name nombre-stack-existente
```

### **Cold Starts en Lambda:**
```bash
# Problema: Primera request es lenta
# Solución: Usar Provisioned Concurrency (no free tier)

# O simplemente esperar - el 99% de requests son rápidos
```

### **DynamoDB "Table does not exist":**
```bash
# Problema: Código busca tabla que no existe
# Solución: Verificar nombres en template.yaml

aws dynamodb list-tables
# Comparar con tu código
```

### **Billing Alerts (IMPORTANTE):**
```bash
# Configurar alerts para no tener sustos
aws budgets create-budget --account-id TU-ACCOUNT-ID --budget '{
  "BudgetName": "StudentBudget",
  "BudgetLimit": {"Amount": "10", "Unit": "USD"},
  "TimeUnit": "MONTHLY",
  "BudgetType": "COST"
}'
```

---

## 📚 Recursos para Profundizar

### **Documentación Oficial (tu biblia):**
- 📖 **AWS Lambda:** https://docs.aws.amazon.com/lambda/
- 📖 **AWS SAM:** https://docs.aws.amazon.com/serverless-application-model/
- 📖 **API Gateway:** https://docs.aws.amazon.com/apigateway/
- 📖 **DynamoDB:** https://docs.aws.amazon.com/dynamodb/

### **Tutoriales Hands-on:**
- 🎓 **AWS Workshop:** https://serverlessland.com/
- 🎓 **SAM Workshop:** https://aws.amazon.com/getting-started/hands-on/build-serverless-app-sam/
- 🎓 **freeCodeCamp:** Buscar "AWS Serverless" en YouTube

### **Herramientas de Desarrollo:**
- 🛠️ **LocalStack:** AWS en tu laptop - https://localstack.cloud/
- 🛠️ **AWS Toolkit:** Para VS Code, IntelliJ - https://aws.amazon.com/toolkit/
- 🛠️ **Postman:** Testing de APIs - https://www.postman.com/
- 🛠️ **Insomnia:** Alternativa a Postman - https://insomnia.rest/

### **Comunidades Activas:**
- 💬 **r/aws** (Reddit) - Preguntas técnicas daily
- 💬 **AWS Community Discord** - Chat real-time con expertos
- 💬 **Serverless Framework Community** - Slack muy activo
- 💬 **DEV.to #serverless** - Artículos y tutoriales

---

## 🎯 Ideas de Proyectos para Practicar

### **🟢 Nivel Principiante (1-2 semanas):**
1. **URL Shortener** - Como bit.ly pero tuyo
2. **QR Code Generator** - API que genere QR codes
3. **Random Quote API** - Base de citas famosas
4. **Password Generator** - API para passwords seguros
5. **Unit Converter** - Métricas, temperaturas, etc.

### **🟡 Nivel Intermedio (2-4 semanas):**
1. **Todo App con Auth** - TaskFlow + Cognito
2. **Image Resizer** - Subir imagen, recibir thumbnail  
3. **Email Sender** - API para enviar emails con SES
4. **Weather Dashboard** - Integración con APIs externas
5. **Expense Tracker** - Con categorías y reportes

### **🟠 Nivel Avanzado (1-2 meses):**
1. **Chat Application** - WebSocket + real-time
2. **File Processing Pipeline** - S3 + Lambda + SNS
3. **Analytics Dashboard** - Ingestión + procesamiento de datos
4. **IoT Data Collector** - Para sensores Arduino/Raspberry Pi
5. **Machine Learning API** - Predicciones con SageMaker

---

## 🏆 Roadmap de Aprendizaje Recomendado

### **📅 Semana 1: Fundamentos**
- [ ] Setup completo de herramientas
- [ ] Deploy exitoso de TaskFlow  
- [ ] Modificar un endpoint existente
- [ ] Entender SAM template básico

### **📅 Semana 2: Exploración**
- [ ] Crear nueva función Lambda desde cero
- [ ] Agregar tabla DynamoDB adicional
- [ ] Implementar nuevo endpoint POST/PUT
- [ ] Probar con diferentes tipos de input

### **📅 Mes 1: Tu Primer Proyecto**
- [ ] Definir idea original simple
- [ ] Diseñar API (3-5 endpoints)
- [ ] Implementar funcionalidades básicas  
- [ ] Deploy en producción + pruebas

### **📅 Mes 2: Seguridad y Auth**
- [ ] Implementar Cognito authentication
- [ ] Configurar WAF básico
- [ ] Tests automatizados
- [ ] Error handling profesional

### **📅 Mes 3: DevOps y Observabilidad**
- [ ] CI/CD pipeline con GitHub Actions
- [ ] CloudWatch dashboards custom
- [ ] Alarmas y notifications
- [ ] Performance optimization

### **📅 Mes 6: Certificación**
- [ ] AWS Cloud Practitioner (fundamentos)
- [ ] AWS Solutions Architect Associate (opcional)
- [ ] Portfolio con 3+ proyectos serverless
- [ ] ¡Buscar trabajo o iniciar startup! 🚀

---

## 💼 Tips para Conseguir Trabajo

### **🎯 Skills más Demandados 2024:**
1. **AWS Lambda + API Gateway** (básico)
2. **Infrastructure as Code** (SAM/CloudFormation)
3. **Cognito Authentication** (security)
4. **CI/CD Pipelines** (DevOps)
5. **Observabilidad** (CloudWatch/X-Ray)

### **📁 Construye tu Portfolio:**
```
📁 Tu GitHub debe tener:
├── 📄 README.md profesional
├── 🚀 2-3 proyectos serverless
├── 📋 Documentación clara de APIs  
├── 🧪 Tests automatizados
└── 🌐 URLs de demos funcionando
```

### **💬 Frases que Impresionan en Entrevistas:**
- "Tengo experiencia deployando infraestructura con Infrastructure as Code"
- "He implementado pipelines CI/CD para deployments automáticos"
- "Conozco el modelo de costos pay-per-use y cómo optimizar"
- "Puedo diseñar APIs que escalen automáticamente de 1 a 1M usuarios"

### **🎓 Certificaciones que Suman:**
- **AWS Cloud Practitioner** - Fundamentos (fácil, 2 semanas estudio)
- **AWS Solutions Architect Associate** - Arquitectura (intermedio)
- **AWS Developer Associate** - Desarrollo (más técnico)

---

## 🚨 Checklist de "Estoy Listo"

### **✅ Antes de aplicar a trabajos:**
- [ ] Tengo 2+ proyectos serverless deployados
- [ ] Entiendo conceptos: Lambda, API Gateway, DynamoDB
- [ ] Puedo explicar diferencia entre serverless y servidores tradicionales
- [ ] Sé configurar autenticación básica
- [ ] He usado IAM roles y policies
- [ ] Entiendo modelos de costos AWS
- [ ] Tengo cuenta GitHub con portfolio visible

### **✅ Señales de que dominas serverless:**
- [ ] Deployeas cambios sin miedo de romper algo
- [ ] Debuggeas problemas usando CloudWatch logs
- [ ] Diseñas APIs pensando en escalabilidad
- [ ] Consideras seguridad desde el diseño
- [ ] Puedes estimar costos de tu aplicación
- [ ] Otros estudiantes te piden ayuda 😄

---

## 📞 ¿Necesitas Ayuda?

### **🆘 Cuando estés atascado:**
1. **Google primero:** "AWS Lambda [tu-error]" 
2. **Stack Overflow:** Comunidad gigante
3. **AWS Re:Post:** Foro oficial de AWS
4. **Discord/Slack:** Comunidades en tiempo real
5. **YouTube:** Tutoriales visuales

### **💡 Recursos de Emergencia:**
- **AWS Free Tier Calculator:** Para no pasarte del límite
- **SAM Troubleshooting:** Docs oficiales muy completas
- **LocalStack:** Para desarrollar sin gastar
- **AWS Support:** Plan básico es gratis

---

<div align="center">

## 🌟 ¡Tu Futuro Serverless Empieza AHORA! 

**Recuerda:** Alex y Sam empezaron exactamente donde estás tú.  
La diferencia entre idea y imperio es **EXECUTION**.

**🚀 ¡Ve y construye algo increíble!**

*Tu próximo deploy podría ser el inicio de la próxima startup unicornio* 🦄

</div>