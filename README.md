# 🏥 Guía de Edición - Fundación VIDARELAX

**"Refugio para el cuerpo, alivio para el alma"**

Esta guía te ayudará a editar el contenido del sitio web de la Fundación VIDARELAX de manera fácil y segura, **sin necesidad de conocimientos técnicos**.

---

## 📋 Tabla de Contenidos

1. [¿Cómo editar el sitio web?](#-cómo-editar-el-sitio-web)
2. [Estructura del proyecto](#-estructura-del-proyecto)
3. [Edición mediante el Panel Administrativo](#-edición-mediante-el-panel-administrativo)
4. [Edición directa de archivos JSON](#-edición-directa-de-archivos-json)
5. [Archivos editables](#-archivos-editables)
6. [Reglas importantes](#-reglas-importantes)
7. [Preguntas frecuentes](#-preguntas-frecuentes)

---

## 🎯 ¿Cómo editar el sitio web?

Hay **DOS formas** de editar el contenido del sitio:

### ✅ **Opción 1: Panel Administrativo (MÁS FÁCIL - RECOMENDADO)**
- Interfaz visual amigable
- No necesitas conocimientos técnicos
- Cambios se publican automáticamente
- **URL:** https://cute-dusk-de1148.netlify.app/admin/

### ✅ **Opción 2: Editar archivos JSON en GitHub**
- Para usuarios con más experiencia
- Editas directamente los archivos de datos
- Requiere conocimientos básicos de JSON
- **URL:** https://github.com/nicolas2456/Fundacion-VIDARELAX

---

## 📁 Estructura del Proyecto

```
Fundacion-VIDARELAX/
│
├── 📄 index.html              # Página principal del sitio web
├── 📄 README.md               # Este archivo (guía de edición)
├── 📄 netlify.toml            # Configuración de despliegue
│
├── 📁 admin/                  # Panel administrativo
│   ├── index.html             # Interfaz del CMS
│   └── config.yml             # Configuración del CMS
│
├── 📁 data/                   # ⭐ ARCHIVOS EDITABLES ⭐
│   ├── general.json           # Información general de la fundación
│   ├── contacto.json          # Datos de contacto
│   ├── mision-vision.json     # Misión, visión y valores
│   ├── como-ayudar.json       # Información de donaciones
│   ├── colores.json           # Paleta de colores del sitio
│   │
│   ├── 📁 junta/              # Miembros de la junta directiva
│   ├── 📁 servicios/          # Servicios ofrecidos
│   └── 📁 documentos/         # Documentos PDF institucionales
│
└── 📁 images/                 # Imágenes y archivos multimedia
    ├── logo.png               # Logo de la fundación
    └── 📁 uploads/            # Imágenes subidas desde el CMS
```

---

## 🖥️ Edición mediante el Panel Administrativo

### **Paso 1: Acceder al Panel**

1. Abre tu navegador y ve a: **https://cute-dusk-de1148.netlify.app/admin/**
2. Inicia sesión con tu correo y contraseña
3. Si es tu primera vez, usa el enlace de invitación que recibiste por correo

### **Paso 2: Seleccionar qué editar**

Una vez dentro, verás las siguientes secciones en el menú lateral:

- **⚙️ Configuración General** - Nombre, NIT, slogan de la fundación
- **🎯 Misión, Visión y Valores** - Identidad institucional
- **👥 Junta Directiva** - Miembros del equipo directivo
- **🏥 Servicios Ofrecidos** - Servicios que presta la fundación
- **📄 Documentos Institucionales** - PDFs y documentos legales
- **🤝 Cómo Ayudar** - Información de donaciones y voluntariado
- **📞 Información de Contacto** - Teléfonos, correos, dirección
- **🎨 Colores y Estilo Visual** - Paleta de colores del sitio

### **Paso 3: Editar el contenido**

1. Haz clic en la sección que quieres editar
2. Haz clic en el elemento específico (verás una vista previa)
3. Edita los campos que necesites cambiar
4. Haz clic en **"Guardar"** (botón verde arriba a la derecha)
5. Luego haz clic en **"Publicar"** para que los cambios sean visibles

### **Paso 4: Verificar los cambios**

1. Espera 1-2 minutos para que el sitio se actualice automáticamente
2. Abre el sitio web en una nueva pestaña: https://cute-dusk-de1148.netlify.app
3. Recarga la página (`F5` o `Ctrl + R`) para ver los cambios

---

## 📝 Edición Directa de Archivos JSON

Si prefieres editar directamente los archivos de datos en GitHub:

### **Paso 1: Acceder a GitHub**

1. Ve a: https://github.com/nicolas2456/Fundacion-VIDARELAX
2. Inicia sesión con tu cuenta de GitHub
3. Navega a la carpeta **`data/`**

### **Paso 2: Editar un archivo**

1. Haz clic en el archivo que quieres editar (ej: `contacto.json`)
2. Haz clic en el ícono del **lápiz** (✏️) arriba a la derecha
3. Edita el contenido respetando el formato JSON
4. Baja hasta el final de la página
5. Escribe un mensaje describiendo el cambio (ej: "Actualizar teléfono de contacto")
6. Haz clic en **"Commit changes"** (botón verde)

### **⚠️ Reglas para editar JSON:**

- **NO elimines las comillas** (`"`)
- **NO elimines las llaves** (`{`, `}`)
- **NO elimines las comas** (`,`)
- Solo edita el **contenido entre comillas**
- Respeta las mayúsculas/minúsculas
- Si tienes dudas, usa el Panel Administrativo en su lugar

### **Ejemplo de edición correcta:**

```json
// ✅ CORRECTO
{
  "telefono": "+57 (314) 817 9078"
}

// ❌ INCORRECTO (falta comilla de cierre)
{
  "telefono": "+57 (314) 817 9078
}

// ❌ INCORRECTO (falta coma entre campos)
{
  "telefono": "+57 (314) 817 9078"
  "email": "contacto@vidarelax.com.co"
}
```

---

## 📄 Archivos Editables

### **1. `/data/general.json` - Información General**

Contiene los datos básicos de la fundación.

**Campos editables:**
- `nombre` - Nombre oficial de la fundación
- `nit` - Número de identificación tributaria
- `slogan` - Frase que identifica a la fundación
- `descripcion` - Descripción breve de la fundación

**Ejemplo:**
```json
{
  "nombre": "VIDARELAX",
  "nit": "901.999.007-7",
  "slogan": "Refugio para el cuerpo, alivio para el alma",
  "descripcion": "Fundación sin ánimo de lucro que brinda apoyo a pacientes oncológicos"
}
```

---

### **2. `/data/contacto.json` - Información de Contacto**

Datos de contacto de la fundación.

**Campos editables:**
- `telefono` - Teléfono principal
- `email_general` - Correo electrónico general
- `email_donaciones` - Correo para donaciones
- `email_voluntariado` - Correo para voluntarios
- `email_pqrs` - Correo para quejas y reclamos
- `email_juridico` - Correo del área jurídica
- `direccion` - Dirección física
- `ciudad` - Ciudad y departamento
- `horario` - Horario de atención

**Ejemplo:**
```json
{
  "telefono": "+57 (314) 817 9078",
  "email_general": "contactanos@vidarelax.com.co",
  "email_donaciones": "donaciones@vidarelax.com.co",
  "direccion": "Carrera 25 #37-13, Barrio Bolívar",
  "ciudad": "Bucaramanga, Santander",
  "horario": "Lunes a Viernes: 8:00 AM - 5:00 PM"
}
```

---

### **3. `/data/mision-vision.json` - Misión, Visión y Valores**

Define la identidad institucional de la fundación.

**Campos editables:**
- `mision` - Razón de ser de la fundación
- `vision` - Aspiración a futuro
- `valores` - Lista de valores institucionales
  - `valor` - Nombre del valor
  - `descripcion` - Explicación del valor

**Ejemplo:**
```json
{
  "mision": "Brindar alojamiento digno y acompañamiento integral a pacientes oncológicos",
  "vision": "Ser la fundación líder en apoyo oncológico en Santander",
  "valores": [
    {
      "valor": "Empatía",
      "descripcion": "Nos ponemos en el lugar de nuestros beneficiarios"
    },
    {
      "valor": "Transparencia",
      "descripcion": "Rendimos cuentas claras de cada donación"
    }
  ]
}
```

---

### **4. `/data/como-ayudar.json` - Cómo Ayudar**

Información sobre donaciones y voluntariado.

**Campos editables:**
- **Sección Donaciones:**
  - `titulo` - Título de la sección
  - `descripcion` - Descripción de cómo donar
  - `cuenta` - Número de cuenta bancaria
  - `nequi` - Número de Nequi

- **Sección Voluntariado:**
  - `titulo` - Título de la sección
  - `descripcion` - Descripción de cómo ser voluntario

**Ejemplo:**
```json
{
  "donaciones": {
    "titulo": "Donaciones",
    "descripcion": "Tu aporte hace la diferencia",
    "cuenta": "Por definir",
    "nequi": "314 817 9078"
  },
  "voluntariado": {
    "titulo": "Voluntariado",
    "descripcion": "Únete a nuestro equipo"
  }
}
```

---

### **5. `/data/colores.json` - Paleta de Colores**

Define los colores institucionales del sitio web.

**⚠️ IMPORTANTE:** Solo edita esto si sabes de códigos de color hexadecimal.

**Campos editables:**
- `color_primario` - Color principal (turquesa)
- `color_secundario` - Color secundario (dorado)
- `color_acento` - Color de acentos (turquesa claro)
- `color_texto` - Color del texto (gris oscuro)

**Ejemplo:**
```json
{
  "color_primario": "#4A7C7E",
  "color_secundario": "#C4A962",
  "color_acento": "#6B9FA1",
  "color_texto": "#2c3e50"
}
```

**📚 Referencia de colores hexadecimales:**
- Los colores se escriben con `#` seguido de 6 caracteres
- Ejemplos: `#FF0000` (rojo), `#00FF00` (verde), `#0000FF` (azul)
- Usa un selector de colores en línea: https://htmlcolorcodes.com/es/

---

### **6. Carpeta `/data/junta/` - Junta Directiva**

Cada miembro de la junta directiva tiene su propio archivo JSON.

**Campos editables:**
- `nombre` - Nombre completo del miembro
- `cargo` - Cargo en la junta directiva
- `foto` - URL de la foto (opcional)
- `bio` - Biografía breve (opcional)

**Ejemplo de archivo:** `/data/junta/presidente.json`
```json
{
  "nombre": "Juan Pérez Gómez",
  "cargo": "Presidente",
  "foto": "/images/uploads/juan-perez.jpg",
  "bio": "Médico oncólogo con 20 años de experiencia"
}
```

---

### **7. Carpeta `/data/servicios/` - Servicios Ofrecidos**

Cada servicio que ofrece la fundación tiene su propio archivo JSON.

**Campos editables:**
- `nombre` - Nombre del servicio
- `icono` - Emoji que representa el servicio
- `descripcion` - Descripción del servicio
- `activo` - Si el servicio está activo (`true` o `false`)

**Ejemplo de archivo:** `/data/servicios/alojamiento.json`
```json
{
  "nombre": "Alojamiento Digno",
  "icono": "🏠",
  "descripcion": "Habitaciones cómodas y seguras para pacientes",
  "activo": true
}
```

**📚 Emojis útiles:**
- 🏠 Casa/Alojamiento
- 🍲 Alimentación
- 🚑 Salud/Médico
- 💊 Medicamentos
- 🤝 Apoyo/Compañía
- 👨‍⚕️ Doctor
- 🧘 Bienestar

---

### **8. Carpeta `/data/documentos/` - Documentos Institucionales**

Cada documento PDF tiene su archivo JSON de referencia.

**Campos editables:**
- `titulo` - Nombre del documento
- `archivo` - Ruta al archivo PDF
- `descripcion` - Descripción del documento
- `categoria` - Categoría (`"Legal"`, `"Transparencia"`, `"Políticas"`, `"Informes"`)

**Ejemplo de archivo:** `/data/documentos/estatutos.json`
```json
{
  "titulo": "Estatutos de la Fundación",
  "archivo": "/documentos/estatutos-vidarelax.pdf",
  "descripcion": "Documento legal que rige el funcionamiento de la fundación",
  "categoria": "Legal"
}
```

---

## ⚠️ Reglas Importantes

### **🚫 NO HAGAS ESTO:**

1. **NO elimines archivos sin consultar** - Podrías romper el sitio web
2. **NO edites archivos `.html`, `.toml`, `.yml`** a menos que sepas lo que haces
3. **NO elimines comillas, llaves o comas en archivos JSON**
4. **NO uses caracteres especiales** en nombres de archivos (usa solo letras, números, guiones)
5. **NO subas archivos muy pesados** (máximo 5 MB por imagen)

### **✅ SÍ DEBES HACER ESTO:**

1. **Usa el Panel Administrativo** siempre que sea posible (es más seguro)
2. **Describe tus cambios** cuando hagas commit en GitHub
3. **Verifica los cambios** en el sitio web después de editar
4. **Haz copias de seguridad** antes de cambios importantes
5. **Pide ayuda** si no estás seguro de algo

---

## ❓ Preguntas Frecuentes

### **¿Cuánto tiempo tardan en verse los cambios?**
Entre 1 y 2 minutos después de guardar. El sitio se actualiza automáticamente.

### **¿Puedo deshacer un cambio?**
Sí, en GitHub puedes ver el historial de cambios y revertir si es necesario.

### **¿Qué pasa si cometo un error?**
No te preocupes. Todos los cambios se guardan en el historial de GitHub. Se puede restaurar versiones anteriores.

### **¿Necesito instalar algo en mi computadora?**
No. Todo se edita en línea a través del navegador (Chrome, Firefox, Edge, etc.).

### **¿Puedo editar desde mi celular?**
Sí, pero es más cómodo hacerlo desde una computadora.

### **¿Quién puede editar el sitio?**
Solo las personas que tengan acceso al Panel Administrativo o a la cuenta de GitHub.

### **¿Cómo agrego una nueva foto?**
Desde el Panel Administrativo, usa el botón "Subir imagen" en cualquier campo de tipo imagen.

### **¿Puedo cambiar los colores del sitio?**
Sí, editando el archivo `/data/colores.json`, pero debes conocer códigos hexadecimales de colores.

### **¿Qué hago si el sitio web deja de funcionar?**
Contacta al desarrollador o revisa el último cambio realizado para revertirlo.

---

## 📞 Contacto y Soporte

**Sitio web:** https://cute-dusk-de1148.netlify.app
**Panel administrativo:** https://cute-dusk-de1148.netlify.app/admin/
**Repositorio GitHub:** https://github.com/nicolas2456/Fundacion-VIDARELAX

**Fundación VIDARELAX:**
- **Teléfono:** +57 (314) 817 9078
- **Email:** contactanos@vidarelax.com.co
- **Ubicación:** Carrera 25 #37-13, Bucaramanga

---

## ✅ Checklist de Edición

Antes de hacer cambios importantes, verifica:

- [ ] Tengo acceso al Panel Administrativo o a GitHub
- [ ] Sé exactamente qué archivo debo editar
- [ ] He leído la documentación de ese archivo
- [ ] Tengo una copia de seguridad (si es un cambio grande)
- [ ] Voy a describir claramente el cambio en el commit
- [ ] Voy a verificar los cambios en el sitio web después

---

**¡Listo! Ahora puedes editar el sitio web de forma segura y sencilla. 🎉**

*"Refugio para el cuerpo, alivio para el alma"*
