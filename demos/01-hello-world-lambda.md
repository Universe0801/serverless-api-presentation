# 🚀 Demo 1: Hello World Lambda en Vivo

> **Slide 6 - Duración: 90 segundos**  
> *Primera demostración de serverless para impactar a la audiencia*

## 🎯 Objetivo de la Demo

**Mostrar la simplicidad extrema de serverless:**
- De 0 a API funcionando en 90 segundos
- Sin configuración de servidores
- Costo $0.00
- URL pública inmediata

## 📝 Script Paso a Paso

### **Preparación (Antes de la charla):**
```bash
# Verificar que AWS CLI esté configurado
aws sts get-caller-identity

# Verificar región correcta
aws configure get region
# Debe ser us-east-1 para demos (más rápido)
```

### **Demo en Vivo (90 segundos):**

#### **1. Apertura impactante (15s)**
```
🎙️ NARRACIÓN:
"Serverless no significa 'sin servidores'. Significa 'sin PREOCUPARSE por servidores. 
Déjenme mostrarles la magia..."

[Abrir AWS Console - ya debe estar logueado]
```

#### **2. Navegación a Lambda (10s)**
```
🎙️ NARRACIÓN:
"Vamos a AWS Lambda. Un click, sin configuración..."

👆 ACCIONES:
1. Click en "Services"
2. Buscar "Lambda" 
3. Click en "AWS Lambda"
```

#### **3. Crear función (20s)**
```
🎙️ NARRACIÓN:
"Create function, selecciono Python porque es rápido de escribir..."

👆 ACCIONES:
1. Click "Create function"
2. Seleccionar "Author from scratch"
3. Function name: "hello-[universidad]" 
   Ejemplo: "hello-unam" o "hello-itesm"
4. Runtime: "Python 3.11"
5. Click "Create function"
```

#### **4. Escribir código (25s)**
```python
import json

def lambda_handler(event, context):
    universidad = "[UNIVERSIDAD]"  # Personalizar
    mensaje = f"¡Hola {universidad}! 🚀 Tu primera API serverless está funcionando!"
    
    return {
        'statusCode': 200,
        'headers': {
            'Content-Type': 'application/json',
            'Access-Control-Allow-Origin': '*'
        },
        'body': json.dumps({
            'message': mensaje,
            'cost': '$0.00',
            'deploy_time': '90_seconds',
            'scaling': 'automatic'
        })
    }
```

```
🎙️ NARRACIÓN mientras escribes:
"Miren qué simple es el código. Solo defino qué quiero que devuelva mi API.
No hay configuración de servidores, no hay Docker, no hay Kubernetes..."

👆 ACCIONES:
1. Reemplazar código default con el de arriba
2. Personalizar [UNIVERSIDAD] con el nombre real
3. Click "Deploy"
```

#### **5. Test en consola (15s)**
```
🎙️ NARRACIÓN:
"Deploy listo. Ahora probemos que funciona..."

👆 ACCIONES:
1. Click en "Test"
2. Si es primera vez: "Configure test event"
   - Event name: "test"
   - Use default template
   - Click "Create"
3. Click "Test" (el botón naranja)
4. Mostrar respuesta exitosa
```

#### **6. URL pública (5s)**
```
🎙️ NARRACIÓN:
"¿Ven? Funciona. Pero esto aún no es una API web. Necesitamos una URL pública..."

👆 ACCIONES:
1. Scroll down hacia "Configuration"
2. Click en "Function URL" 
3. Click "Create function URL"
4. Auth type: "NONE"
5. Click "Save"
```

#### **7. Test público + BOOM moment (10s)**
```
🎙️ NARRACIÓN:
"¡Y ahí está! Una URL pública mundial..."

👆 ACCIONES:
1. Copy la URL que aparece
2. Abrir nueva tab en el browser
3. Pegar URL y ENTER
4. Mostrar respuesta JSON funcionando

🎙️ CIERRE IMPACTANTE:
"¿Vieron eso? 90 segundos. API funcionando. URL pública. Escalable a millones de usuarios. 
Costo hasta ahora: $0.00"
```

## 🔥 Elementos de Impacto

### **Frases clave durante la demo:**
- "Sin configuración de servidores"
- "No hay Docker, no hay Kubernetes"
- "Escalable a millones automáticamente"
- "Costo: $0.00"
- "URL pública mundial en 90 segundos"

### **Gestos y énfasis:**
- Mostrar las manos cuando digas "sin configuración"
- Hacer pausa dramática después del ENTER final
- Sonreír cuando aparezca la respuesta JSON

## 🚨 Planes de Backup

### **Plan B: Si AWS Console está lento**
```
🎙️ SCRIPT ALTERNATIVO:
"Veo que AWS está un poco lento hoy. Esto pasa en demos en vivo..."

👆 ACCIÓN:
1. Cambiar a screenshots preparados (ver backup-screenshots/)
2. Narrar cada paso con las imágenes
3. Mostrar código en editor local
4. "En condiciones normales esto toma 90 segundos exactos"
```

### **Plan C: Si no hay internet**
```
🎙️ SCRIPT ALTERNATIVO:
"Perfecto momento para demostrar que estas cosas pasan. Por eso en producción 
necesitamos redundancia..."

👆 ACCIÓN:
1. Mostrar código en editor local
2. Explicar cada línea
3. "Cuando regrese internet, haremos el deploy real"
4. Continuar con siguiente slide
```

## 📸 Screenshots de Backup

**Preparar antes de la presentación:**
1. `aws-console-lambda-home.png` - Página inicial de Lambda
2. `create-function-screen.png` - Pantalla de crear función
3. `code-editor-with-hello-code.png` - Editor con código hello world
4. `test-result-success.png` - Resultado exitoso del test
5. `function-url-creation.png` - Creación de URL pública
6. `browser-json-response.png` - Respuesta final en browser

## 🎯 Mensajes Clave que Debe Recordar la Audiencia

1. **Simplicidad:** "Solo código de negocio, cero configuración"
2. **Velocidad:** "90 segundos de idea a producción"
3. **Costo:** "$0.00 para empezar"
4. **Escalabilidad:** "Millones de usuarios automáticamente"
5. **Global:** "URL mundial desde minuto 1"

## ⚡ Transición al Siguiente Slide

```
🎙️ SCRIPT DE TRANSICIÓN:
"Esto que acabamos de ver en 90 segundos es exactamente lo que descubrieron Alex y Sam. 
Pero ellos no se quedaron ahí. Tenían una idea más ambiciosa..."

[Pasar a Slide 7 - Conoce a TaskFlow]
```

## 🔧 Troubleshooting Rápido

**Si aparece error de permisos:**
- "Perfecto, esto es muy real. En producción configuramos IAM roles..."
- Usar screenshots de backup

**Si la función no responde:**
- "Esto es exactamente por qué necesitamos observabilidad..."
- Mostrar CloudWatch logs rápidamente

**Si la audiencia hace preguntas técnicas:**
- "Excelente pregunta, la vamos a ver en detalle en 20 minutos cuando lleguemos al Acto II"

---

*🎯 Esta demo es el 'hook' de toda la presentación. Debe ser perfecta.*  
*⏱️ Practicar mínimo 5 veces antes de presentar en público.*