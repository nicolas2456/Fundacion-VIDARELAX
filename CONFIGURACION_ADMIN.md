# 🔐 Configuración del Panel Administrativo

## ✅ Cambios Realizados

El panel administrativo ahora utiliza **Netlify Identity** para autenticación simple con **email y contraseña**, eliminando la necesidad de que los fundadores tengan cuentas de GitHub.

### Ventajas:
- ✅ Login simple con email y contraseña
- ✅ No requiere conocimientos de GitHub
- ✅ Interfaz intuitiva en `/admin`
- ✅ Totalmente **GRATIS** (hasta 1000 usuarios)
- ✅ Los cambios se guardan automáticamente en el repositorio

---

## 📋 Pasos de Configuración (Una sola vez)

### **PASO 1: Crear Sitio en Netlify** (5 minutos)

Aunque la página está en Vercel, necesitamos Netlify SOLO para el servicio de autenticación (es gratis).

1. **Ve a Netlify**:
   - Abre: https://app.netlify.com/signup
   - Regístrate con tu cuenta de **GitHub** (la misma del repositorio)
   - Es **TOTALMENTE GRATIS**

2. **Importa el repositorio**:
   - Click en **"Add new site"** → **"Import an existing project"**
   - Click en **"GitHub"**
   - Autoriza a Netlify acceso a tus repositorios
   - Busca y selecciona: **nicolas2456/Fundacion-VIDARELAX**

3. **Configura el sitio**:
   - **Site name**: `vidarelax-identity` (o el que prefieras)
   - **Branch to deploy**: `main`
   - **Build command**: (déjalo vacío)
   - **Publish directory**: `.` (punto)
   - Click en **"Deploy site"**

4. **Anota la URL**:
   - Te dará una URL como: `https://vidarelax-identity.netlify.app`
   - **Guarda esta URL**, la necesitarás en el siguiente paso

---

### **PASO 2: Activar Netlify Identity** (3 minutos)

1. **En el dashboard de Netlify**, ve a tu sitio recién creado

2. **Activa Identity**:
   - Click en el menú lateral: **"Site configuration"** → **"Identity"**
   - Click en **"Enable Identity"**

3. **Configura Git Gateway**:
   - En la misma página de Identity, busca la sección **"Services"**
   - Click en **"Enable Git Gateway"**
   - Esto permite que el CMS guarde cambios en GitHub automáticamente

---

### **PASO 3: Configurar Opciones de Registro** (2 minutos)

1. **En Identity**, ve a **"Settings and usage"**

2. **Registration preferences**:
   - Selecciona: **"Invite only"** (Solo por invitación)
   - Esto asegura que solo personas autorizadas puedan acceder

3. **External providers** (opcional):
   - Puedes dejar Google activado si quieres permitir login con Google
   - O desactivarlo para solo usar email/contraseña

4. **Emails** (opcional):
   - Netlify enviará emails de confirmación desde su servidor
   - Puedes personalizar las plantillas si quieres (no es necesario)

---

### **PASO 4: Invitar a los Administradores** (2 minutos por persona)

1. **En Netlify**, ve a **"Site configuration"** → **"Identity"** → **"Invite users"**

2. **Invita a cada fundador**:
   - Ingresa el **email** del fundador
   - Click en **"Send invite"**
   - Repite para cada persona que necesite acceso (Daniel y los demás fundadores)

3. **Los fundadores recibirán un email**:
   - Título: "You've been invited to join..."
   - Deben hacer click en **"Accept the invite"**
   - Crearán su contraseña
   - ¡Listo! Ya pueden acceder

---

### **PASO 5: Configurar Vercel con Netlify Identity** (3 minutos)

Para que el panel `/admin` en tu sitio de Vercel funcione con Netlify Identity:

1. **Abre el archivo**: `index.html` en tu repositorio

2. **Busca la línea 21** (aproximadamente):
   ```html
   <script src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
   ```
   ✅ Ya está agregado, no necesitas hacer nada

3. **Agrega variable de entorno en Vercel** (IMPORTANTE):
   - Ve a tu proyecto en Vercel
   - **Settings** → **Environment Variables**
   - Agrega:
     - **Name**: `NETLIFY_SITE_URL`
     - **Value**: `https://vidarelax-identity.netlify.app` (la URL de tu sitio Netlify del Paso 1)
   - Click **"Save"**

4. **Redeploy en Vercel**:
   - Ve a **"Deployments"**
   - Click en el último deployment → **"Redeploy"**

---

## 🎯 Cómo Usar el Panel Administrativo

### **Para los Fundadores (muy simple):**

1. **Acceder al panel**:
   - Abre en tu navegador: `https://fundacion-vidarelax-pzue.vercel.app/admin`
   - O cuando se conecte el dominio: `https://www.vidarelax.com.co/admin`

2. **Iniciar sesión**:
   - La primera vez, haz click en el enlace del email de invitación
   - Crea tu contraseña
   - Las siguientes veces, solo ingresa email y contraseña

3. **Editar contenido**:
   - Verás un panel con secciones como:
     - ⚙️ Configuración General
     - 🎯 Misión, Visión y Valores
     - 👥 Junta Directiva
     - 🏥 Servicios Ofrecidos
     - 📄 Documentos Institucionales
     - 💝 Cómo Ayudar
     - 📞 Información de Contacto
     - 🎨 Colores y Estilo Visual

4. **Subir documentos o imágenes**:
   - Entra a la sección correspondiente
   - Click en **"New documento"** (o la opción correspondiente)
   - Llena los campos
   - Sube el archivo PDF o imagen
   - Click en **"Publish"**
   - ¡Los cambios se subirán automáticamente a la página!

5. **Editar textos**:
   - Click en la sección que quieres editar
   - Click en el elemento específico
   - Modifica el texto
   - Click en **"Publish"**
   - Los cambios estarán en vivo en 1-2 minutos

---

## ⚙️ Archivos Modificados

- ✅ `admin/config.yml`: Cambiado de `github` a `git-gateway`
- ✅ `admin/index.html`: Agregado Netlify Identity widget
- ✅ `index.html`: Ya incluye script de Netlify Identity

---

## 🔧 Solución de Problemas

### **Problema: "No se puede iniciar sesión"**
- Verifica que Git Gateway esté activado en Netlify
- Verifica que la variable de entorno `NETLIFY_SITE_URL` esté configurada en Vercel
- Asegúrate de que el usuario fue invitado correctamente

### **Problema: "Los cambios no se guardan"**
- Verifica que Git Gateway tenga acceso al repositorio
- Ve a Netlify → Identity → Services → Git Gateway y verifica el estado

### **Problema: "Email de invitación no llega"**
- Revisa la carpeta de spam
- Verifica que el email esté escrito correctamente
- Reenvía la invitación desde Netlify

---

## 💡 Notas Importantes

1. **Solo configuras Netlify UNA VEZ** - después todo funciona automático
2. **La página sigue en Vercel** - Netlify solo se usa para autenticación
3. **Es totalmente GRATIS** - ambos servicios (Netlify Identity y Vercel) son gratuitos
4. **Los fundadores NO necesitan GitHub** - solo email y contraseña
5. **Los cambios son automáticos** - cuando publican en el CMS, se actualizan en GitHub y Vercel despliega automáticamente

---

## 📞 Soporte

Si tienes algún problema durante la configuración:
1. Revisa cada paso cuidadosamente
2. Verifica que Git Gateway esté activado
3. Asegúrate de que las variables de entorno estén configuradas

---

**¡Tu panel administrativo ahora es súper simple y accesible para todos los fundadores!** 🎉
