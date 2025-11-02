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

## ⚠️ IMPORTANTE: Cuenta NUEVA de Netlify

**¿Por qué cuenta nueva?**
- Ya tuviste problemas de límite de crédito en la cuenta anterior de Netlify
- Esta cuenta nueva **SOLO se usará para Identity (autenticación)**
- **NO vamos a desplegar nada** en Netlify (el hosting sigue en Vercel)
- Es un servicio separado = no hay problema de límites

**Opciones de email para la cuenta nueva:**
- Email personal del cliente/fundador
- Tu email secundario
- Crear un Gmail nuevo: `vidarelax.admin@gmail.com`
- Cualquier email diferente al que usaste en la cuenta anterior

---

## 📋 Pasos de Configuración (Una sola vez)

### **PASO 1: Crear NUEVA Cuenta en Netlify** (5 minutos)

⚠️ **MUY IMPORTANTE:** Usa un email **DIFERENTE** al de la cuenta anterior que tuvo problemas.

1. **Ve a Netlify**:
   - Abre: https://app.netlify.com/signup
   - **Regístrate con un EMAIL NUEVO** (no el que usaste antes)
   - Puedes usar:
     - Email del cliente
     - Tu email secundario
     - Crear Gmail nuevo ahora mismo
   - Es **TOTALMENTE GRATIS** y sin límites para Identity

2. **Importa el repositorio** (solo para conectar con GitHub):
   - Click en **"Add new site"** → **"Import an existing project"**
   - Click en **"GitHub"**
   - Autoriza a Netlify acceso a tus repositorios
   - Busca y selecciona: **nicolas2456/Fundacion-VIDARELAX**

3. **Configura el sitio** (NO te preocupes por el despliegue):
   - **Site name**: `vidarelax-identity` (o el que prefieras)
   - **Branch to deploy**: `main`
   - **Build command**: (déjalo vacío)
   - **Publish directory**: `.` (punto)
   - Click en **"Deploy site"**

   ℹ️ **NOTA:** El sitio se desplegará pero NO lo vamos a usar. Solo necesitamos que exista para activar Identity. La página real sigue en Vercel.

4. **Anota la URL del sitio Netlify**:
   - Te dará una URL como: `https://vidarelax-identity.netlify.app`
   - **Guarda esta URL**, la necesitarás en el PASO 5
   - ⚠️ **NO compartas esta URL con nadie** - es solo para configuración interna

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

## ❓ Preguntas Frecuentes (FAQ)

### **¿No habíamos tenido problemas con Netlify por límite de crédito?**

**Sí**, pero esta solución NO tiene ese problema porque:

1. ✅ **Cuenta NUEVA** - Usamos un email diferente = cuenta nueva sin límites consumidos
2. ✅ **Solo Identity** - NO usamos hosting de Netlify (el que consume créditos)
3. ✅ **Identity es gratis** - Hasta 1000 usuarios, sin cargos ni límites de bandwidth
4. ✅ **Hosting en Vercel** - La página sigue en Vercel (ilimitado y gratis)

**En resumen:**
- Cuenta anterior: Usaba hosting + forms + CMS = consumió créditos ❌
- Cuenta nueva: Solo usa Identity (autenticación) = 0 consumo ✅

### **¿Por qué no usar solo GitHub para login?**

GitHub requiere que los fundadores:
- Creen cuenta GitHub
- Entiendan conceptos técnicos
- Sepan qué es un repositorio

Con Netlify Identity:
- Solo necesitan email y contraseña (como cualquier sitio web)
- Interfaz familiar y simple
- No necesitan saber de programación

### **¿Cuánto cuesta Netlify Identity?**

**GRATIS** hasta 1000 usuarios activos al mes.
- Fundación tendrá 2-3 usuarios máximo
- Muy por debajo del límite gratuito
- No hay cargos ocultos

### **¿Qué pasa si la cuenta nueva también se queda sin créditos?**

**No pasará** porque:
- NO vamos a usar hosting en esta cuenta
- Solo usamos Identity (servicio separado, sin límites)
- El tráfico de la página va a Vercel (ilimitado)

### **¿Los visitantes del sitio verán algo de Netlify?**

**NO**. Solo los administradores verán el login de Netlify Identity en `/admin`.
Los visitantes normales solo ven la página de Vercel en www.vidarelax.com.co

---

## 📞 Soporte

Si tienes algún problema durante la configuración:
1. Revisa cada paso cuidadosamente
2. Verifica que Git Gateway esté activado
3. Asegúrate de que las variables de entorno estén configuradas
4. Confirma que estás usando una cuenta NUEVA de Netlify

---

**¡Tu panel administrativo ahora es súper simple y accesible para todos los fundadores!** 🎉

**Resumen:** Netlify = Solo login | Vercel = Toda la página ✅
