# 📊 Documentación de Archivos JSON - VIDARELAX

Esta carpeta contiene todos los archivos de datos del sitio web de la Fundación VIDARELAX.

**IMPORTANTE:** JSON no permite comentarios dentro de los archivos. Esta guía documenta el propósito y estructura de cada archivo.

---

## 📄 `general.json` - Información General de la Fundación

**Propósito:** Almacena la información institucional básica de la fundación.

**Estructura:**
```json
{
  "nombre": "Nombre oficial de la fundación",
  "nit": "Número de identificación tributaria (formato: XXX.XXX.XXX-X)",
  "slogan": "Frase corta que identifica a la fundación",
  "descripcion": "Descripción breve de la fundación (1-2 frases)"
}
```

**Dónde se usa:**
- Header del sitio web
- Sección "Acerca de"
- Footer
- Metadata del sitio

**Reglas de edición:**
- El NIT debe mantener el formato con puntos y guión
- El slogan debe ser corto (máximo 60 caracteres)
- La descripción debe ser concisa y clara

---

## 📞 `contacto.json` - Información de Contacto

**Propósito:** Almacena todos los datos de contacto de la fundación.

**Estructura:**
```json
{
  "telefono": "Número de teléfono principal (formato: +57 (XXX) XXX XXXX)",
  "email_general": "Correo electrónico general de contacto",
  "email_donaciones": "Correo específico para temas de donaciones",
  "email_voluntariado": "Correo específico para voluntarios",
  "email_pqrs": "Correo para peticiones, quejas, reclamos y sugerencias",
  "email_juridico": "Correo del área jurídica o legal",
  "direccion": "Dirección física completa (calle, número, barrio)",
  "ciudad": "Ciudad y departamento (formato: Ciudad, Departamento)",
  "horario": "Horario de atención (formato: Días: Hora - Hora)"
}
```

**Dónde se usa:**
- Sección de contacto del sitio
- Footer del sitio
- Formularios de contacto
- Botón flotante de WhatsApp

**Reglas de edición:**
- Todos los correos deben ser válidos y estar activos
- El teléfono debe incluir código de país (+57 para Colombia)
- El horario debe ser claro y específico

---

## 🎯 `mision-vision.json` - Misión, Visión y Valores

**Propósito:** Define la identidad institucional y los principios de la fundación.

**Estructura:**
```json
{
  "mision": "Razón de ser de la fundación (qué hacemos y para quién)",
  "vision": "Aspiración a futuro (cómo queremos que sea la fundación en el futuro)",
  "valores": [
    {
      "valor": "Nombre del valor (ej: Empatía, Transparencia)",
      "descripcion": "Explicación breve de qué significa ese valor para la fundación"
    }
  ]
}
```

**Dónde se usa:**
- Sección "Misión y Visión" del sitio
- Página "Acerca de"
- Documentos institucionales

**Reglas de edición:**
- La misión debe responder: ¿Qué hacemos? ¿Para quién? ¿Cómo lo hacemos?
- La visión debe ser aspiracional y orientada al futuro
- Valores: Se pueden agregar o eliminar valores según necesidad
- Cada valor debe tener nombre y descripción claros

**Cómo agregar un nuevo valor:**
```json
{
  "valor": "Compromiso",
  "descripcion": "Dedicación total a nuestros beneficiarios"
}
```

Agregar una coma después del último valor existente y añadir el nuevo objeto.

---

## 🤝 `como-ayudar.json` - Información de Donaciones y Voluntariado

**Propósito:** Proporciona información sobre cómo las personas pueden apoyar a la fundación.

**Estructura:**
```json
{
  "donaciones": {
    "titulo": "Título de la sección de donaciones",
    "descripcion": "Mensaje motivacional sobre las donaciones",
    "cuenta": "Número de cuenta bancaria (incluir banco y tipo de cuenta)",
    "nequi": "Número de teléfono Nequi (solo números)"
  },
  "voluntariado": {
    "titulo": "Título de la sección de voluntariado",
    "descripcion": "Mensaje sobre cómo ser voluntario"
  }
}
```

**Dónde se usa:**
- Sección "Cómo Ayudar" del sitio
- Página de donaciones
- Información de voluntariado

**Reglas de edición:**
- La cuenta bancaria debe incluir: banco, tipo de cuenta, número
- El número Nequi debe estar activo y verificado
- Las descripciones deben ser motivacionales y claras
- Si no hay cuenta bancaria aún, dejar como "Por definir"

---

## 🎨 `colores.json` - Paleta de Colores Institucionales

**Propósito:** Define los colores que se usan en todo el sitio web.

**Estructura:**
```json
{
  "color_primario": "Color principal del sitio (formato hexadecimal: #XXXXXX)",
  "color_secundario": "Color secundario para acentos (formato hexadecimal: #XXXXXX)",
  "color_acento": "Color para botones y elementos destacados (formato hexadecimal: #XXXXXX)",
  "color_texto": "Color del texto principal (formato hexadecimal: #XXXXXX)"
}
```

**Dónde se usa:**
- En todo el sitio web
- Botones, enlaces, fondos
- Headers y footers
- Elementos decorativos

**Reglas de edición:**
- Los colores DEBEN estar en formato hexadecimal (#XXXXXX)
- Usar un selector de colores para obtener el código: https://htmlcolorcodes.com/es/
- Asegurarse de que los colores tengan buen contraste con el fondo
- El color de texto debe ser oscuro para buena legibilidad

**Ejemplos de códigos de color:**
- `#4A7C7E` - Turquesa oscuro (color primario actual)
- `#C4A962` - Dorado suave (color secundario actual)
- `#FFFFFF` - Blanco
- `#000000` - Negro
- `#2c3e50` - Gris oscuro (texto actual)

**⚠️ PRECAUCIÓN:** Cambiar estos colores afectará TODO el sitio web. Asegúrate de que los nuevos colores se vean bien en todas las secciones antes de publicar.

---

## 📁 Carpeta `junta/` - Miembros de la Junta Directiva

**Propósito:** Almacena información de cada miembro de la junta directiva.

**Estructura de cada archivo:**
```json
{
  "nombre": "Nombre completo del miembro",
  "cargo": "Cargo en la junta directiva (ej: Presidente, Secretario, Tesorero)",
  "foto": "Ruta a la foto del miembro (ej: /images/uploads/nombre.jpg) - OPCIONAL",
  "bio": "Biografía breve del miembro (educación, experiencia) - OPCIONAL"
}
```

**Nombre de archivo sugerido:** `nombre-cargo.json` (ej: `maria-perez-presidente.json`)

**Dónde se usa:**
- Sección "Junta Directiva" del sitio
- Página "Quiénes Somos"

**Reglas de edición:**
- Cada miembro debe tener su propio archivo JSON
- El nombre del archivo debe ser descriptivo (sin espacios, usar guiones)
- La foto es opcional, pero mejora la presentación
- La biografía debe ser profesional y relevante

**Cómo agregar un nuevo miembro:**
1. Crear un nuevo archivo en la carpeta `junta/`
2. Nombrarlo según el patrón: `nombre-cargo.json`
3. Copiar la estructura JSON de arriba
4. Llenar los datos del nuevo miembro
5. Si tiene foto, subirla primero a `/images/uploads/`

**Cómo eliminar un miembro:**
- Simplemente eliminar el archivo JSON correspondiente

---

## 🏥 Carpeta `servicios/` - Servicios Ofrecidos

**Propósito:** Almacena información sobre cada servicio que ofrece la fundación.

**Estructura de cada archivo:**
```json
{
  "nombre": "Nombre del servicio",
  "icono": "Emoji que representa el servicio (ej: 🏠, 🍲, 💊)",
  "descripcion": "Descripción detallada del servicio (qué incluye, cómo funciona)",
  "activo": true o false (si el servicio está actualmente disponible)
}
```

**Nombre de archivo sugerido:** `nombre-del-servicio.json` (ej: `alojamiento-digno.json`)

**Dónde se usa:**
- Sección "Servicios" del sitio principal
- Tarjetas de servicios

**Reglas de edición:**
- Cada servicio debe tener su propio archivo JSON
- El icono debe ser un emoji único que represente bien el servicio
- La descripción debe ser clara y específica (2-4 frases)
- `activo: true` = El servicio se muestra en el sitio
- `activo: false` = El servicio está oculto (pero no eliminado)

**Emojis recomendados para servicios:**
- 🏠 Alojamiento/Hospedaje
- 🍲 Alimentación/Comida
- 🚑 Transporte/Ambulancia
- 💊 Medicamentos/Farmacia
- 🤝 Acompañamiento/Apoyo
- 👨‍⚕️ Atención médica
- 🧘 Terapias/Bienestar
- 📚 Educación/Capacitación
- 🎨 Arte terapia
- 💰 Apoyo económico

**Cómo agregar un nuevo servicio:**
1. Crear un nuevo archivo en la carpeta `servicios/`
2. Nombrarlo descriptivamente (sin espacios, usar guiones)
3. Copiar la estructura JSON
4. Llenar los datos del servicio
5. Elegir un emoji apropiado
6. Poner `activo: true` para que se muestre

**Cómo desactivar un servicio temporalmente:**
- En lugar de eliminar el archivo, cambiar `activo: true` a `activo: false`

---

## 📄 Carpeta `documentos/` - Documentos Institucionales

**Propósito:** Almacena referencias a documentos PDF institucionales que los usuarios pueden descargar.

**Estructura de cada archivo:**
```json
{
  "titulo": "Nombre descriptivo del documento",
  "archivo": "Ruta al archivo PDF (ej: /documentos/nombre-documento.pdf)",
  "descripcion": "Breve descripción del contenido del documento",
  "categoria": "Categoría del documento: Legal, Transparencia, Políticas o Informes"
}
```

**Nombre de archivo sugerido:** `nombre-documento.json` (ej: `estatutos-2024.json`)

**Dónde se usa:**
- Sección "Documentos" o "Transparencia" del sitio
- Página de descargas
- Footer (documentos legales)

**Categorías disponibles:**
- **"Legal"** - Estatutos, certificados, registro legal, etc.
- **"Transparencia"** - Estados financieros, informes de donaciones, etc.
- **"Políticas"** - Políticas de privacidad, tratamiento de datos, etc.
- **"Informes"** - Informes anuales, reportes de gestión, etc.

**Reglas de edición:**
- Cada documento PDF debe tener su archivo JSON de referencia
- El archivo PDF debe estar en la carpeta `/documentos/`
- La categoría DEBE ser una de las 4 opciones exactas (con mayúscula inicial)
- El título debe ser claro y descriptivo

**Cómo agregar un nuevo documento:**
1. Subir el PDF a la carpeta `/documentos/` del repositorio
2. Crear un archivo JSON en `data/documentos/`
3. Nombrarlo similar al PDF (ej: si el PDF es `estatutos.pdf`, el JSON puede ser `estatutos.json`)
4. Copiar la estructura JSON
5. Llenar los datos, asegurándose de que la ruta del archivo sea correcta

**Ejemplo completo:**
```json
{
  "titulo": "Estatutos de la Fundación VIDARELAX 2024",
  "archivo": "/documentos/estatutos-vidarelax-2024.pdf",
  "descripcion": "Documento legal que establece el marco normativo de la fundación",
  "categoria": "Legal"
}
```

**Cómo eliminar un documento:**
1. Eliminar el archivo JSON en `data/documentos/`
2. Opcionalmente, eliminar el PDF de `/documentos/` (no es obligatorio)

---

## 🔧 Consejos Generales para Editar JSON

### ✅ **Buenas Prácticas:**

1. **Siempre usa comillas dobles** (`"`) para cadenas de texto, nunca comillas simples (`'`)
2. **No pongas coma después del último elemento** de un objeto o array
3. **Respeta la indentación** para mantener el código legible
4. **Verifica que no falten llaves o corchetes** (`{`, `}`, `[`, `]`)
5. **Usa un validador JSON** si tienes dudas: https://jsonlint.com/

### ❌ **Errores Comunes:**

1. **Olvidar comillas de cierre:**
   ```json
   // ❌ INCORRECTO
   "nombre": "VIDARELAX

   // ✅ CORRECTO
   "nombre": "VIDARELAX"
   ```

2. **Poner coma en el último elemento:**
   ```json
   // ❌ INCORRECTO
   {
     "nombre": "VIDARELAX",
     "nit": "901.999.007-7",
   }

   // ✅ CORRECTO
   {
     "nombre": "VIDARELAX",
     "nit": "901.999.007-7"
   }
   ```

3. **No cerrar llaves o corchetes:**
   ```json
   // ❌ INCORRECTO
   {
     "valores": [
       {"valor": "Empatía"}
   }

   // ✅ CORRECTO
   {
     "valores": [
       {"valor": "Empatía"}
     ]
   }
   ```

4. **Usar comillas simples en lugar de dobles:**
   ```json
   // ❌ INCORRECTO
   {'nombre': 'VIDARELAX'}

   // ✅ CORRECTO
   {"nombre": "VIDARELAX"}
   ```

---

## 🛡️ Seguridad y Backups

### **Antes de editar:**
- Revisa bien qué archivo vas a editar
- Asegúrate de entender el propósito del archivo
- Si no estás seguro, usa el Panel Administrativo en su lugar

### **Después de editar:**
- Verifica que el archivo JSON sea válido (sin errores de sintaxis)
- Espera 1-2 minutos y revisa el sitio web
- Si algo sale mal, puedes revertir el cambio en GitHub (ver historial)

### **Backups automáticos:**
- GitHub guarda automáticamente cada versión de cada archivo
- Puedes ver el historial completo de cambios
- Puedes restaurar cualquier versión anterior si es necesario

---

## 📞 ¿Necesitas Ayuda?

Si tienes dudas sobre cómo editar algún archivo:

1. **Consulta el README.md principal** en la raíz del proyecto
2. **Usa el Panel Administrativo** en lugar de editar JSON directamente
3. **Valida tu JSON** en https://jsonlint.com/ antes de guardar
4. **Revisa ejemplos** en otros archivos similares de la misma carpeta
5. **Contacta al desarrollador** si el problema persiste

---

**¡Recuerda!**

El Panel Administrativo (https://cute-dusk-de1148.netlify.app/admin/) es **más seguro y fácil** que editar JSON directamente. Solo edita archivos JSON si tienes experiencia o si el Panel Administrativo no está disponible.

*"Refugio para el cuerpo, alivio para el alma"*
