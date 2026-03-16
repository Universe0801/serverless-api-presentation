# 🚲 BLOQUE 2: ACTO I - EL MVP

> **Slides 7-13 | Duración: 20 minutos**  
> *La historia de TaskFlow y el demo más importante*

---

## Slide 7: Conoce a TaskFlow
**⏱️ Duración: 2 minutos**

### **📄 Contenido del Slide:**
```markdown
🎬 ACTO I: La Gran Idea

Personajes principales:
👨‍💻 Alex Chen - Estudiante de CS, quinto semestre
👩‍🎨 Sam Rivera - Estudiante de Diseño, frustrated con apps existentes

🎯 LA VISIÓN:
"Una API de tareas tan simple que cualquier developer 
pueda integrarla en 5 minutos"

💰 RECURSOS:
• Presupuesto total: $100 (de vender libros usados)
• Tiempo disponible: 2 semanas (periodo vacacional)  
• Conocimientos: Java básico, una clase de bases de datos
• Objetivo: Validar idea con MVP real

⏰ PRESIÓN: Demo en hackathon universitario
```

### **🎨 Especificaciones Visuales:**
- **Layout:** Comic/manga style con viñetas para cada personaje
- **Personajes:** 
  - Alex: Avatar masculino con laptop, código en pantalla
  - Sam: Avatar femenina con tablet de diseño, sketches
- **Elementos:**
  - Speech bubbles con la visión
  - Calculadora mostrando $100
  - Calendario con "2 semanas" marcado
  - Cronómetro de countdown para hackathon
- **Colores:** Azul (tech), Rosa (design), Verde (dinero)
- **Estilo:** Flat design moderno, friendly y relatable

### **🎙️ Script:**
> "Alex y Sam podrían ser cualquiera de ustedes. Alex sabía Java porque llevó POO, Sam entendía lo que los usuarios realmente necesitan. Entre los dos tenían 100 dólares y una teoría: 'Las apps de tareas existentes son demasiado complicadas'."

---

## Slide 8: Arquitectura MVP - Los 4 Pilares
**⏱️ Duración: 3 minutos**

### **📄 Contenido del Slide:**
```markdown
🏗️ Arquitectura MVP: Elegancia en la Simplicidad

📱 API Gateway → La puerta de entrada
   🌐 URL automática, CORS incluido, throttling gratis

⚡ AWS Lambda → El cerebro (Java 21)
   🧠 Solo código de negocio, escalado automático

🗄️ DynamoDB → La memoria  
   📊 NoSQL, pay-per-use, backup automático

👀 CloudWatch → Los ojos
   📈 Logs, métricas, alertas - todo incluido

💰 COSTO TOTAL MENSUAL: $0-5 (Free Tier)
⚡ CAPACIDAD: 1,000 req/seg out-of-the-box
🛡️ SEGURIDAD: HTTPS por defecto
```

### **🎨 Especificaciones Visuales:**
- **Layout:** 4 pilares como templo griego con iconos AWS
- **Elementos centrales:**
  - API Gateway: Puerta dorada con flujos de datos
  - Lambda: Cerebro con rayos de energía
  - DynamoDB: Base de datos con flechas dinámicas  
  - CloudWatch: Ojo grande observando todo
- **Conexiones:** Flechas bidireccionales mostrando comunicación
- **Métricas:** Boxes destacados para costo, capacidad, seguridad
- **Animación:** Revelar cada pilar secuencialmente
- **Colores AWS:** Naranja (Lambda), Verde (API GW), Azul (DynamoDB), Rojo (CloudWatch)

### **🎙️ Script:**
> "Alex investigó por 3 días y descubrió algo increíble: AWS había resuelto TODOS los problemas técnicos que los estaban asustando. ¿Necesitas un servidor web? API Gateway te da uno configurado."

---

## Slide 9: Demo - El Repositorio Real
**⏱️ Duración: 4 minutos**

### **📄 Contenido del Slide:**
```markdown
💻 DEMO: Explorando el Código TaskFlow

🔗 github.com/universe-org/serverless-api-demo

📂 Estructura súper simple:
├── 📄 template.yaml      # 🏗️ Infraestructura como código
├── 📄 pom.xml           # ☕ Dependencias Java  
├── 📁 src/              # 💼 Código de negocio
└── 📄 README.md         # 📚 Tu guía de supervivencia

🎯 TODO el proyecto: 4 archivos principales
⏰ Setup time: 5 minutos
🧠 Complejidad: Junior-friendly

🎬 DEMO EN VIVO: Navegación por GitHub
```

### **🎨 Especificaciones Visuales:**
- **Layout:** Split screen - GitHub real (izquierda) + explicación (derecha)
- **Screen recording:** Preparar navegación por el repo
- **File tree:** Visualización clara de estructura simple
- **Highlights:** 
  - Resaltar template.yaml
  - Mostrar tamaño de archivos (pequeños)
  - Enfatizar simplicidad vs complejidad tradicional
- **Comparación:** Sidebar con "Proyecto tradicional" vs "TaskFlow"
- **Animación:** Hover effects en archivos importantes

### **🎙️ Script + Demo:**
> "Vamos a ver el código REAL que construyeron Alex y Sam. Esto no es un ejemplo de tutorial, es código que maneja millones de requests en producción."
> 
> **[DEMO EN VIVO según demos/01-hello-world-lambda.md]**

---

## Slide 10: SAM Template Explicado
**⏱️ Duración: 3 minutos**

### **📄 Contenido del Slide:**
```yaml
# template.yaml - La Magia Explicada ✨

Resources:
  # 📊 Base de datos sin configuración
  TasksTable:
    Type: AWS::DynamoDB::Table
    BillingMode: PAY_PER_REQUEST  # Solo pagas por uso real
    
  # 🌐 API web automática
  TasksApi:
    Type: AWS::Serverless::Api
    Cors: '*'                     # Acceso desde cualquier web
    
  # ⚡ Función que maneja requests
  TasksFunction:
    Type: AWS::Serverless::Function
    Runtime: java21               # ¡La última versión!
    Handler: com.example.TasksHandler::handleRequest
    Events:
      - Type: Api
        Path: /tasks              # Automáticamente crea el endpoint
```

### **🎨 Especificaciones Visuales:**
- **Layout:** Code editor realista con syntax highlighting
- **Elementos:**
  - YAML properly formatted
  - Annotations/callouts para cada sección  
  - Side comments explicando cada línea
  - Comparison box: "30 líneas SAM = 200+ líneas CloudFormation"
- **Highlighting:** Resaltar PAY_PER_REQUEST, java21, Api events
- **Animation:** Typewriter effect revelando código línea por línea
- **Background:** Dark code editor theme (VS Code style)

### **🎙️ Script:**
> "Este archivo YAML es literalmente toda la infraestructura. ¿Ven esa simplicidad? No hay configuración de red, no hay security groups, no hay load balancers. SAM toma esto y genera automáticamente CloudFormation template de 200+ líneas."

---

## Slide 11: Los 5 Endpoints CRUD
**⏱️ Duración: 2 minutos**

### **📄 Contenido del Slide:**
```markdown
🔌 API Endpoints - El Contrato Perfecto

POST   /tasks              → ➕ Crear nueva tarea
GET    /tasks/{id}         → 🔍 Obtener tarea específica  
GET    /tasks              → 📋 Listar todas las tareas
PUT    /tasks/{id}         → ✏️ Actualizar tarea existente
DELETE /tasks/{id}         → 🗑️ Eliminar tarea

💡 UNA función Lambda maneja TODOS los endpoints
🎯 Routing automático por método HTTP
📝 JSON request/response estándar

🌐 Ejemplo: https://api.taskflow.com/tasks
```

### **🎨 Especificaciones Visuales:**
- **Layout:** API documentation style con colores HTTP
- **Métodos HTTP:** Color coding (POST=green, GET=blue, PUT=orange, DELETE=red)
- **Iconos:** Emojis correspondientes a cada acción
- **Request/Response:** Mockup de JSON examples
- **Flow diagram:** Una Lambda → múltiples endpoints
- **URL example:** Realistic API URL highlighted
- **Postman mockup:** Screenshot style de API testing

### **🎙️ Script:**
> "Alex diseñó la API siguiendo estándares REST que cualquier developer reconoce al instante. No hay endpoints raros, no hay convenciones custom. Lo inteligente: una sola función Lambda maneja todos los endpoints."

---

## Slide 12: Demo - Deploy en Vivo ⭐ 
**⏱️ Duración: 4 minutos**

### **📄 Contenido del Slide:**
```markdown
🚀 DEMO: De Código a Producción Mundial

Comandos que cambiarán tu vida:

$ sam build                    # 🔨 Compila Java + dependencias
$ sam deploy --guided         # 🚀 Primera vez: configuración  
$ sam deploy                  # ⚡ Siguientes: un solo comando

⏱️ Tiempo total: ~3 minutos
💰 Costo: $0.00 (Free Tier)
🌍 Disponibilidad: Global desde minuto 1
📊 Monitoring: Automático e incluido

🎬 DEPLOY EN VIVO - Sin red de seguridad
```

### **🎨 Especificaciones Visuales:**
- **Layout:** Terminal real ocupando 70% del slide
- **Terminal:** Dark theme con output real de SAM
- **Progress indicators:** 
  - Build progress bar
  - Deploy status updates
  - Success checkmarks
- **Side panel:** Timing, costs, features appearing
- **Countdown:** Timer visible mostrando tiempo transcurrido
- **Warning banner:** "DEMO EN VIVO" prominente
- **Backup ready:** Screenshots discretamente disponibles

### **🎙️ Script + Demo:**
> "Momento de la verdad. Vamos a deployar TaskFlow desde cero, en vivo, sin red de seguridad."
> 
> **[DEMO EN VIVO crítico según demos/02-sam-deploy-live.md]**

---

## Slide 13: Resultado del MVP
**⏱️ Duración: 2 minutos**

### **📄 Contenido del Slide:**
```markdown
🎉 MVP Exitoso - Alex y Sam Celebran

📊 Logros en 15 minutos:
✅ API REST funcionando
✅ URL pública: https://xyz.execute-api.us-east-1.amazonaws.com/dev
✅ Escalabilidad automática incluida
✅ SSL/HTTPS por defecto
✅ Logs y métricas profesionales  
✅ Backup automático de datos

💰 Costo real primer mes: $0.00
📈 Capacidad: 1,000 req/seg sin configuración
🏆 Demo en hackathon: 🥇 Primer lugar
💡 Validación: 50+ developers piden acceso

🎯 "No habían construido solo un proyecto de clase. 
    Habían construido un producto real."
```

### **🎨 Especificaciones Visuales:**
- **Layout:** Celebration theme con confetti y success elements
- **Characters:** Alex y Sam celebrando (high-five o thumbs up)
- **Achievements:** Badge-style accomplishments
- **Real URL:** Actual functioning URL highlighted
- **Metrics dashboard:** Mini CloudWatch-style charts
- **Trophy:** First place hackathon trophy prominent
- **Quote box:** Final quote in elegant typography
- **Transition:** Setup for next act with "but success brings new challenges..."

### **🎙️ Script:**
> "Alex y Sam no podían creer lo que habían logrado. En 15 minutos tenían una API más robusta que startups con equipos de 10 personas. El hackathon fue un éxito total. Ahí se dieron cuenta: no habían construido solo un proyecto de clase. Habían construido un producto real."

---

## 🎨 Assets Necesarios para Acto I

### **📸 Imágenes Principales:**
1. **alex-sam-characters.png** - Personajes estilizados con laptops/tablets
2. **architecture-4-pillars.png** - Templo con 4 pilares AWS services
3. **github-repo-mockup.png** - Clean GitHub interface screenshot
4. **yaml-code-editor.png** - Syntax highlighted YAML in editor
5. **api-endpoints-diagram.png** - REST API documentation style
6. **terminal-demo-screen.png** - Terminal con SAM deploy output
7. **celebration-success.png** - Alex y Sam celebrando MVP

### **📊 Diagramas Técnicos:**
1. **taskflow-architecture-v1.png** - Simple 4-component architecture
2. **sam-vs-cloudformation.png** - 30 lines vs 200+ lines comparison
3. **cost-breakdown-mvp.png** - AWS Free Tier breakdown
4. **scalability-chart.png** - 1 → 1000 req/seg automatic

### **🎬 Elementos Interactivos:**
1. **typing-animation.css** - Typewriter effect para código
2. **progress-bars.js** - Build/deploy progress indicators
3. **confetti-celebration.js** - Success celebration animation
4. **architecture-reveal.css** - Sequential pillar revelation

---

## 🛠️ Templates de Slide específicos

### **Template: Slide 8 (Arquitectura)**
```html
<!-- PowerPoint/Google Slides Layout -->
<div class="architecture-slide">
  <div class="pillars-container">
    <div class="pillar api-gateway">
      <icon>🌐</icon>
      <title>API Gateway</title>
      <description>URL automática, CORS incluido</description>
    </div>
    <div class="pillar lambda">
      <icon>⚡</icon>
      <title>AWS Lambda</title>
      <description>Solo código de negocio</description>
    </div>
    <!-- ... más pilares -->
  </div>
  <div class="benefits-bar">
    <metric>$0-5/mes</metric>
    <metric>1K req/seg</metric>
    <metric>HTTPS default</metric>
  </div>
</div>
```

### **Template: Slide 12 (Demo Terminal)**
```html
<div class="demo-slide">
  <div class="terminal-window">
    <div class="terminal-header">
      <span class="title">Terminal - SAM Deploy Live</span>
    </div>
    <div class="terminal-body">
      <div class="command-line">$ sam build</div>
      <div class="output">Building codeuri...</div>
      <!-- Más output real -->
    </div>
  </div>
  <div class="demo-stats">
    <div class="timer">⏱️ 02:47</div>
    <div class="cost">💰 $0.00</div>
    <div class="status">🟢 Deploying...</div>
  </div>
</div>
```

---

## 📝 Instrucciones Específicas para Diseñadores

### **🎨 Para Slide 7 (Personajes):**
```
Estilo: Flat design, friendly, diversity-conscious
Alex: 
- Asiático, 20-22 años, casual wear (hoodie/t-shirt)
- Laptop abierto con código Java visible
- Expresión: concentrado pero optimista

Sam:
- Latina, 20-22 años, creative style
- Tablet con sketches/wireframes
- Expresión: creativa y determinada

Setting: Universidad moderna, maybe coffee shop
Mood: Collaborative, aspirational, relatable
```

### **🏗️ Para Slide 8 (Arquitectura):**
```
Concepto: Templo griego moderno con pilares tech
Pilares: Mismo height, diferentes colores AWS
Conexiones: Subtle dotted lines entre servicios
Base: Solid foundation labeled "AWS Free Tier"
Background: Clean white/light gray gradient
Typography: Sans-serif, clear hierarchy
```

### **💻 Para Slide 12 (Terminal Demo):**
```
Terminal: macOS/Ubuntu style, dark theme
Font: Menlo/Monaco monospace, 14pt
Colors: Green text on black background
Window: Realistic terminal window with controls
Output: Real SAM deploy output (get from actual run)
Timing: Visible timer in corner
Status: Progress indicators for each step
```

---

## ⚠️ Puntos Críticos de Éxito

### **🔥 Demo Slide 12 - CRÍTICO:**
- **Preparar 3 planes de backup** (live, screenshots, video)
- **Practicar 10+ veces** antes de presentación real
- **Tener internet backup** (hotspot móvil)
- **AWS account working** y configurado previamente

### **💡 Storytelling Consistency:**
- Mantener a Alex y Sam como protagonistas
- Timeline claro: 2 semanas → hackathon → éxito
- Conectar cada slide con "la historia continúa..."
- Preparar transición dramática al Acto II

### **🎯 Audience Engagement Checkpoints:**
- **Slide 7:** "¿Cuántos se identifican con Alex/Sam?"
- **Slide 10:** "¿Alguien había visto YAML tan simple?"  
- **Slide 12:** "¿Están listos para la magia en vivo?"
- **Slide 13:** "¿Qué creen que pasó después del éxito?"

---

*⚡ Siguiente: [Slides 14-19: Acto II - El Crecimiento](03-acto-2-crecimiento.md)*