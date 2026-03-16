# ⏱️ Guía de Timing Detallada - "De la Idea al Imperio"

> **Control de tiempo preciso para presentación de 60 minutos**  
> *Incluye tiempos de backup, ajustes en tiempo real y señales de la audiencia*

## 📊 Resumen Ejecutivo de Tiempo

| **Bloque** | **Tiempo** | **Slides** | **Tipo** | **Backup Plan** |
|------------|------------|------------|----------|-----------------|
| 🔥 **Introducción** | 10 min | 1-6 | Engagement + Demo | Skip slide 2 (bio) |
| 🚲 **ACTO I: MVP** | 20 min | 7-13 | Historia + Demo live | Acortar demo repo |
| 🔒 **ACTO II: Crecimiento** | 15 min | 14-19 | Evolución + Seguridad | Skip demo WAF |
| 🏢 **ACTO III: Escala** | 10 min | 20-24 | DevOps + Métricas | Combinar 23-24 |
| 🎯 **Cierre** | 5 min | 25-27 | Call to Action | Solo slide 26 |
| ❓ **Q&A** | 15 min | 28 | Interactivo | Extender si engagement alto |

**⏰ TIEMPO TOTAL: 60 minutos exactos**

---

## 🔥 BLOQUE 1: INTRODUCCIÓN (10 minutos)

### **Control Granular por Slide**

| **Slide** | **Tiempo** | **Actividad Principal** | **Si vas lento** | **Si vas rápido** |
|-----------|------------|-------------------------|------------------|-------------------|
| **1** | 1 min | Hook + presentación | Directo al punto | Agregar humor |
| **2** | 1 min | Bio personal | **SKIP** si atrasado | Conectar más con audiencia |
| **3** | 1 min | Promesa de valor | Mantener | Enfatizar empleabilidad |
| **4** | 2 min | Agenda narrativa | Acortar a 90s | Agregar suspense |
| **5** | 2 min | Problema universal | Mantener | Más interacción |
| **6** | 3 min | Demo Hello World | **CRÍTICO** - no cortar | Agregar segundo ejemplo |

### **🚨 Señales de Ajuste**

**🟢 Audiencia comprometida (continúa normal):**
- Contacto visual activo
- Toman notas o fotos
- Risas en momentos de humor
- Preguntas espontáneas

**🟡 Audiencia perdida (acelera):**
- Caras confusas
- Conversaciones paralelas
- Revisión constante de teléfonos
- **ACCIÓN:** Skip slide 2, acortar slide 4 a 90s

**🔴 Audiencia aburrida (cambia estrategia):**
- Bostezos
- Postura cerrada
- Salidas frecuentes
- **ACCIÓN:** Ir directo al demo (slide 6), más interacción

---

## 🚲 BLOQUE 2: ACTO I - MVP (20 minutos)

### **Control Granular por Slide**

| **Slide** | **Tiempo** | **Actividad** | **Plan B** | **Plan C** |
|-----------|------------|---------------|------------|------------|
| **7** | 2 min | Historia TaskFlow | Mantener | Más detalles personajes |
| **8** | 3 min | Arquitectura MVP | Mantener | Diagrama más detallado |
| **9** | 4 min | **Demo repo navegación** | Screenshots | Solo README |
| **10** | 3 min | SAM template | Acortar a 2 min | Skip si muy técnico |
| **11** | 2 min | Endpoints CRUD | Mantener | Agregar ejemplo request |
| **12** | 4 min | **Deploy en vivo** | Screenshots + explicación | Video pregrabado |
| **13** | 2 min | Métricas MVP | Mantener | Enfatizar éxito |

### **🔧 Manejo de Demos Críticas**

**Demo Slide 9 (Navegación GitHub):**
- ⏱️ **Tiempo máximo:** 4 minutos
- 🎯 **Objetivo:** Mostrar simplicidad del código
- 📱 **Plan B:** Screenshots navegación preparados
- 📹 **Plan C:** Solo README + template.yaml
- ⚠️ **Red flag:** Si GitHub está lento, ir inmediato a Plan B

**Demo Slide 12 (SAM Deploy):**
- ⏱️ **Tiempo máximo:** 4 minutos
- 🎯 **Objetivo:** Deploy real en producción
- 📱 **Plan B:** Screenshots de cada paso + narración
- 📹 **Plan C:** Video pregrabado de 2 minutos
- ⚠️ **Preparación:** Tener AWS CLI configurado, repo clonado

### **🎪 Puntos de Engagement**

**Minuto 15 - Checkpoint obligatorio:**
> "¿Alguien había visto antes que 4 archivos fueran toda una infraestructura?"

**Minuto 25 - Transición dramática:**
> "Alex y Sam no podían creer que en 15 minutos tenían algo mejor que startups con equipos de 10 personas."

---

## 🔒 BLOQUE 3: ACTO II - CRECIMIENTO (15 minutos)

### **Control Granular por Slide**

| **Slide** | **Tiempo** | **Actividad** | **Si atrasado** | **Si adelantado** |
|-----------|------------|---------------|-----------------|-------------------|
| **14** | 2 min | Problema del éxito | Mantener | Más drama |
| **15** | 3 min | Evolución arquitectural | Mantener | Comparación visual |
| **16** | 3 min | Cognito auth | Mantener | Detalles técnicos |
| **17** | 2 min | WAF seguridad | Mantener | Ejemplos ataques |
| **18** | 3 min | **Demo seguridad** | **SKIP** completo | Demo extendida |
| **19** | 2 min | Métricas v2 | Mantener | Impacto business |

### **⚡ Ajustes de Velocidad**

**Si vas 2+ minutos atrasado:**
1. Skip completamente slide 18 (demo seguridad)
2. Acortar slide 17 a 90 segundos
3. Combinar explicación de Cognito + WAF en 4 min total

**Si vas adelantado:**
1. Demo seguridad completa con Postman
2. Mostrar logs en tiempo real en CloudWatch
3. Agregar ejemplo de ataque bloqueado

### **🎭 Transición Crítica (Minuto 40)**
> "Con seguridad enterprise, TaskFlow se convirtió en opción confiable para clientes serios. Pero aún faltaba el salto final: escala corporativa."

---

## 🏢 BLOQUE 4: ACTO III - ESCALA (10 minutos)

### **Control Granular por Slide**

| **Slide** | **Tiempo** | **Actividad** | **Compresión** | **Expansión** |
|-----------|------------|---------------|----------------|---------------|
| **20** | 2 min | Enterprise requisitos | Mantener | Más ejemplos clientes |
| **21** | 3 min | DevOps transformación | Mantener | Detalles pipeline |
| **22** | 2 min | Pipeline código | Mantener | Explicar cada job |
| **23** | 2 min | Métricas unicornio | Mantener | Comparar industry |
| **24** | 1 min | Stack final | Combinar con 23 | Roadmap detallado |

### **🚀 Manejo de Climax**

**Minuto 50 - Punto culminante:**
- Enfatizar la transformación completa: $100 → $1B
- Conectar con el inicio: "Dos estudiantes como ustedes"
- Preparar transición emocional al cierre

**Si audiencia muy técnica:**
- Más tiempo en slide 21 (DevOps)
- Detalles específicos de observabilidad

**Si audiencia más business:**
- Más tiempo en slide 23 (métricas financieras)
- Impacto en valoración e IPO

---

## 🎯 BLOQUE 5: CIERRE (5 minutos)

### **Control Granular por Slide**

| **Slide** | **Tiempo** | **Actividad** | **Mínimo** | **Óptimo** |
|-----------|------------|---------------|------------|------------|
| **25** | 2 min | 5 lecciones | Mantener | Conectar con historia |
| **26** | 2 min | **Call to action** | **CRÍTICO** | Más incentivos |
| **27** | 1 min | Recursos | Skip si atrasado | Lista detallada |

### **🔥 Call to Action - NO NEGOCIABLE**

**Slide 26 es el más importante:**
- Deadline específico: "próximo lunes"
- Incentivo real: "primeros 10 feedback personalizado"
- Acción clara: "Fork + deploy + modificar + redeploy"

**Si solo tienes 2 minutos:**
- Solo slide 26
- Skip lecciones y recursos
- Directo al compromiso de acción

---

## ❓ BLOQUE 6: Q&A (15 minutos)

### **Estrategia de Manejo**

**Primeros 5 minutos:**
- Preguntas técnicas específicas
- Respuestas detalladas con ejemplos

**Minutos 5-10:**
- Preguntas de carrera/empleabilidad
- Experiencias personales

**Últimos 5 minutos:**
- Preguntas conceptuales
- Visión de futuro de serverless

### **🎯 Preguntas Frecuentes con Timings**

| **Pregunta** | **Tiempo respuesta** | **Elementos clave** |
|--------------|----------------------|---------------------|
| "¿Serverless más caro?" | 2-3 min | Casos de uso, comparación real |
| "¿Cold starts?" | 1-2 min | Provisioned concurrency, reality check |
| "¿Debuging sin servers?" | 2-3 min | X-Ray, CloudWatch, herramientas |
| "¿Skills para trabajo?" | 1-2 min | Certificaciones, portafolio |

---

## 🚨 PLANES DE CONTINGENCIA

### **Si vas MUY atrasado (5+ minutos):**

**Plan de Compresión Extrema:**
1. Skip slides 2, 10, 18, 24, 27
2. Demos solo con screenshots
3. Combinar slides 22+23+24 en uno
4. Q&A solo 10 minutos

### **Si vas MUY adelantado (5+ minutos):**

**Plan de Expansión:**
1. Demo completa Hello World + deploy en slide 6
2. Demo navegación código más detallada en slide 9
3. Demo seguridad completa en slide 18
4. Q&A extendido hasta 20 minutos
5. Sesión informal post-charla

### **Si hay problemas técnicos:**

**Backup Strategy:**
1. **Sin internet:** Screenshots de todas las demos en slides ocultos
2. **AWS lento:** Videos pregrabados de 1-2 minutos
3. **Proyector falla:** Narración pura + engagement interactivo
4. **Todo falla:** Historia TaskFlow como storytelling puro

---

## 📊 MÉTRICAS DE TIMING EN TIEMPO REAL

### **Checkpoints Obligatorios:**

- ✅ **Minuto 10:** Completar introducción + hook establecido
- ✅ **Minuto 30:** ACTO I completado + demo MVP exitosa
- ✅ **Minuto 45:** ACTO II completado + seguridad clara
- ✅ **Minuto 55:** ACTO III + call to action entregado
- ✅ **Minuto 60:** Q&A iniciado con energía alta

### **Señales de Audiencia por Timing:**

**Minuto 15:** Si no hay engagement, acelerar
**Minuto 30:** Si hay muchas preguntas, es buen signo
**Minuto 45:** Si audiencia cansada, más humor e interacción
**Minuto 55:** Si muy comprometidos, Q&A puede extenderse

---

## 🎪 FÓRMULAS DE AJUSTE RÁPIDO

### **Para acelerar (+2 min):**
```
- Skip slide 2 (bio)
- Combinar slides 22+23 
- Demo screenshots en lugar de live
- Acortar Q&A a 12 min
```

### **Para desacelerar (-2 min):**
```
+ Más humor en slide 5
+ Demo extendida en slide 12
+ Interacción en cada acto
+ Q&A extender a 18 min
```

### **Señales de "wrap up":**
- Personas revisan relojes
- Movimiento inquieto
- Susurros sobre tiempo

**Acción inmediata:** Ir directo al call to action (slide 26)

---

*⏱️ Esta guía debe estar accesible durante la presentación para ajustes en tiempo real*  
*🎯 El éxito se mide en engagement + call to action completion, no en completar todos los slides*