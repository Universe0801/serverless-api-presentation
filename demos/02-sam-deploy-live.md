# 🚀 Demo 2: SAM Deploy en Vivo - TaskFlow MVP

> **Slide 12 - Duración: 4 minutos**  
> *La demo más importante: de código a producción mundial*

## 🎯 Objetivo de la Demo

**Mostrar el poder real de SAM:**
- Infraestructura compleja deployada en minutos
- Una sola línea de comando para crear 15+ recursos AWS
- API REST completa funcionando
- Base de datos, monitoring, y seguridad incluidos

## 🛠️ Preparación Previa (30 min antes de la charla)

### **Setup obligatorio:**
```bash
# 1. Verificar herramientas instaladas
aws --version                 # AWS CLI v2.x
sam --version                 # SAM CLI v1.x
java -version                 # Java 21+
mvn --version                 # Maven 3.8+

# 2. Configurar AWS
aws configure list
aws sts get-caller-identity

# 3. Limpiar deployments previos (si existen)
aws cloudformation delete-stack --stack-name taskflow-demo-[universidad]
aws cloudformation wait stack-delete-complete --stack-name taskflow-demo-[universidad]

# 4. Preparar directorio limpio
rm -rf taskflow-demo/
```

### **Pre-clonado estratégico:**
```bash
# Clonar y preparar en directorio temporal
git clone https://github.com/universe-org/serverless-api-demo.git taskflow-demo
cd taskflow-demo

# Pre-build para descargar dependencias (acelera demo)
sam build

# Verificar que funciona
ls -la .aws-sam/build/
```

## 📝 Script de Demo en Vivo

### **1. Introducción dramática (30s)**
```
🎙️ NARRACIÓN:
"Alex investigó por 3 días y descubrió algo increíble: AWS había resuelto TODOS los 
problemas técnicos que los estaban asustando."

"Momento de la verdad. Vamos a deployar TaskFlow desde cero, en vivo, sin red de seguridad."

👆 PREPARACIÓN:
- Terminal ya abierto en directorio limpio
- GitHub ya abierto en https://github.com/universe-org/serverless-api-demo
```

### **2. Clonar repositorio (45s)**
```bash
# Comando 1
git clone https://github.com/universe-org/serverless-api-demo.git taskflow-[universidad]

# Comando 2  
cd taskflow-[universidad]

# Comando 3
ls -la
```

```
🎙️ NARRACIÓN mientras clona:
"Primero clonamos el repositorio de TaskFlow. Este es el código real que manejan 
millones de requests."

🎙️ MIENTRAS HACE ls -la:
"Miren qué simple: template.yaml define la infraestructura, src/ tiene el código Java, 
pom.xml las dependencias. TODO el proyecto son 4 archivos principales."
```

### **3. Mostrar template.yaml (30s)**
```bash
# Comando 4
cat template.yaml | head -20
```

```
🎙️ NARRACIÓN:
"Este archivo YAML es literalmente toda la infraestructura. ¿Ven esa simplicidad? 
No hay configuración de red, no hay security groups, no hay load balancers.

SAM toma esto y genera automáticamente un CloudFormation template de 200+ líneas. 
Ustedes escriben 30 líneas, AWS hace el trabajo pesado."
```

### **4. Build del proyecto (60s)**
```bash
# Comando 5
sam build
```

```
🎙️ NARRACIÓN mientras builda:
"sam build compila Java y resuelve dependencias. Maven está descargando las librerías 
de AWS SDK automáticamente..."

[Mientras espera - 30-45 segundos]

"Esto está compilando el JAR, empaquetando todo lo que necesita la Lambda, y 
preparando el deployment package."

🎙️ CUANDO TERMINE:
"¡Perfecto! Build exitoso. Ahora viene la magia..."
```

### **5. Deploy con --guided (90s)**
```bash
# Comando 6
sam deploy --guided
```

```
🎙️ NARRACIÓN:
"sam deploy --guided para configurar por primera vez..."

📋 RESPUESTAS A PROMPTS:
Stack Name: taskflow-demo-[universidad]
AWS Region: us-east-1
Environment: dev
Confirm changes before deploy: Y
Allow SAM CLI IAM role creation: Y
Disable rollback: N
Save parameters to samconfig.toml: Y
Deploy this changeset: y
```

```
🎙️ NARRACIÓN DURANTE DEPLOY (60-90s):
"AWS está creando 15+ recursos automáticamente:
- DynamoDB table para almacnar tareas
- API Gateway para los endpoints REST  
- Lambda function para la lógica de negocio
- CloudWatch logs para monitoring
- IAM roles para seguridad
- Todo conectado y configurado automáticamente"

"En una empresa tradicional, esto tomaría días o semanas de configuración manual..."
```

### **6. ¡BOOM! Resultados (30s)**
```
🎙️ CUANDO TERMINE EL DEPLOY:
"¡BOOM! Deploy exitoso. Miren los outputs..."

👁️ MOSTRAR EN TERMINAL:
- ApiGatewayUrl: https://xyz.execute-api.us-east-1.amazonaws.com/dev
- TasksTableName: taskflow-demo-universidad-tasks-dev
- Environment: dev

🎙️ CIERRE IMPACTANTE:
"¿Tiempo total? 3 minutos y 45 segundos. 
¿Costo? $0.00. 
¿Capacidad? 1,000 requests por segundo out-of-the-box.
¿Disponibilidad? Global, ahora mismo."
```

### **7. Test rápido de la API (45s)**
```bash
# Comando 7 - Guardar URL
API_URL=$(aws cloudformation describe-stacks \
  --stack-name taskflow-demo-[universidad] \
  --query 'Stacks[0].Outputs[?OutputKey==`ApiGatewayUrl`].OutputValue' \
  --output text)

# Comando 8 - Test crear tarea
curl -X POST $API_URL/tasks \
  -H "Content-Type: application/json" \
  -d '{"title":"Mi primera tarea serverless","description":"Deployada en vivo desde [universidad]!"}'

# Comando 9 - Test listar tareas  
curl $API_URL/tasks
```

```
🎙️ NARRACIÓN FINAL:
"Y aquí está: nuestra API funcionando en producción. Acabamos de crear una tarea 
y listarla. Esta URL es accesible desde cualquier parte del mundo, ahora mismo."

"Alex y Sam no podían creer lo que habían logrado. En 4 minutos tenían una API 
más robusta que startups con equipos de 10 personas."
```

## 🔥 Elementos Críticos de Éxito

### **Frases de impacto obligatorias:**
- "Sin red de seguridad"
- "Código real de producción"  
- "AWS está creando 15+ recursos automáticamente"
- "En empresa tradicional esto tomaría días"
- "Costo: $0.00"
- "Global, ahora mismo"

### **Timing crítico:**
- **Total máximo:** 4 minutos
- **Build:** 60 segundos max
- **Deploy:** 90 segundos max  
- **Test:** 45 segundos max

## 🚨 Planes de Backup

### **Plan B: Si el build falla**
```bash
# Usar directorio pre-preparado
cd ../taskflow-demo-backup/
sam deploy --guided  # Skip el build
```

```
🎙️ SCRIPT:
"Perfecto, esto es desarrollo real. Por eso Alex pre-compiló todo..."
[Cambiar a directorio backup]
"En producción siempre tienes backup plans."
```

### **Plan C: Si el deploy falla**
```
🎙️ SCRIPT:
"¡Excelente! Acabamos de ver por qué necesitamos CI/CD robusto. 
Esto es exactamente lo que vamos a ver en el Acto III."

👆 ACCIÓN:
1. Mostrar screenshots del deploy exitoso
2. Usar URL pre-deployada de backup
3. Continuar con tests usando API existente
```

### **Plan D: Si no hay internet**
```
🎙️ SCRIPT:
"Esta es la razón perfecta para mostrar por qué necesitamos multi-region deployment..."

👆 ACCIÓN:
1. Screenshots de todo el proceso
2. Video pregrabado de 2 minutos
3. Mostrar código local en editor
```

## 📊 Comandos de Backup Pre-preparados

```bash
# API URL de backup (deploy antes de la charla)
BACKUP_API="https://xyz123.execute-api.us-east-1.amazonaws.com/dev"

# Test inmediato si falla deploy
curl $BACKUP_API/tasks

# Cleanup rápido si algo sale mal
aws cloudformation delete-stack --stack-name taskflow-demo-[universidad]
```

## 🎯 Mensajes Clave

1. **Velocidad:** "4 minutos de código a producción mundial"
2. **Simplicidad:** "Un comando, 15+ recursos AWS"
3. **Robustez:** "Más robusto que equipos de 10 personas"
4. **Costo:** "$0.00 para empezar"
5. **Escalabilidad:** "1,000 req/seg sin configuración"

## ⚡ Transición Perfect al Slide 13

```
🎙️ SCRIPT DE TRANSICIÓN:
"Alex y Sam no podían creer el resultado. Habían construido en 4 minutos 
lo que les habría tomado semanas usando métodos tradicionales.

El hackathon fue un éxito total. No solo ganaron, sino que 50 developers 
se acercaron preguntando cuándo iba a estar disponible la API.

Ahí se dieron cuenta: no habían construido solo un proyecto de clase. 
Habían construido un producto real."

[Pasar a Slide 13 - Resultado del MVP]
```

## 🔧 Troubleshooting en Tiempo Real

**Si AWS está lento:**
- "Esto pasa cuando todo el mundo está haciendo demos al mismo tiempo..."
- Mostrar screenshots mientras espera

**Si aparecen errores de permisos:**
- "Perfecto timing para hablar de IAM y seguridad..."
- Usar como setup para Acto II

**Si la audiencia se ve perdida:**
- Hacer pausa: "¿Preguntas hasta aquí?"
- Repetir los puntos clave lentamente

**Si van muy rápido:**
- Mostrar la consola AWS durante el deploy
- Explicar cada recurso que se está creando

---

*🚀 Esta es la demo que define toda la presentación*  
*⏱️ PRACTICAR mínimo 10 veces con diferentes conexiones de internet*  
*💡 Tener 3 cuentas AWS diferentes como backup*