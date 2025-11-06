# 🔐 INSTRUCCIONES PARA CONFIGURAR ACCESO ADMINISTRATIVO

## ✅ ESTADO ACTUAL DEL CÓDIGO

**TODO ESTÁ LISTO EN EL CÓDIGO:**
- ✅ Netlify CMS (Decap CMS) ya está configurado
- ✅ Panel administrativo en `/admin/` funcionando
- ✅ Scripts de Netlify Identity incluidos
- ✅ Git Gateway configurado

**SOLO FALTA:** Configurar Netlify Identity en Vercel para activar los usuarios.

---

## 👥 USUARIOS A CREAR:

1. **contactanos@vidarelax.com.co**
   - Contraseña temporal: `VidaRelax2024!Admin`
   - ⚠️ IMPORTANTE: Cambiar esta contraseña después del primer login

2. **lastradanieleduardo@gmail.com**
   - El cliente Daniel creará su propia contraseña al recibir la invitación

---

## 📋 PASO 1: ACCEDER AL DASHBOARD DE VERCEL

1. Ve a: **https://vercel.com**
2. Inicia sesión con tu cuenta
3. Selecciona el proyecto: **fundacion-vidarelax** (o el nombre que le hayas dado)

---

## 🔧 PASO 2: HABILITAR NETLIFY IDENTITY EN VERCEL

### Opción A: Si Vercel tiene integración de Netlify Identity

Vercel NO tiene Netlify Identity nativo, así que necesitamos usar **Netlify** para la autenticación.

### Opción B: Usar Netlify para Identity (RECOMENDADO)

**Como el sitio está alojado en Vercel, necesitamos:**

1. **Crear una cuenta en Netlify:**
   - Ve a: https://app.netlify.com/signup
   - Regístrate con tu email (gratis, no pagarás nada)
   - Confirma tu email

2. **Importar el repositorio de GitHub a Netlify:**

   a) En Netlify, haz clic en "Add new site" → "Import an existing project"

   b) Conecta con GitHub y selecciona el repositorio: `nicolas2456/Fundacion-VIDARELAX`

   c) **IMPORTANTE:** En la configuración de build:
   - Build command: `echo "No build needed"`
   - Publish directory: `.` (punto)
   - Branch to deploy: `main`

   d) Haz clic en "Deploy site"

   e) **NO USES ESTE SITIO DE NETLIFY** - Solo lo usamos para Netlify Identity

3. **Habilitar Netlify Identity:**

   a) En el dashboard de Netlify, ve a: **Site configuration** → **Identity**

   b) Haz clic en **"Enable Identity"**

   c) En **Registration preferences**, selecciona: **"Invite only"** (solo por invitación)

   d) En **External providers**, puedes dejarlo deshabilitado (no necesitamos login con Google/GitHub)

   e) En **Git Gateway**, haz clic en **"Enable Git Gateway"**

   f) Selecciona el rol: **"Open Git Gateway to anyone with a valid Identity user account"**

---

## 📧 PASO 3: INVITAR USUARIOS

### Usuario 1: contactanos@vidarelax.com.co (TÚ TIENES ACCESO)

1. En Netlify, ve a: **Site configuration** → **Identity** → **"Invite users"**

2. Ingresa el email: `contactanos@vidarelax.com.co`

3. Haz clic en **"Send invitation"**

4. **IMPORTANTE:** El email de invitación llegará a `contactanos@vidarelax.com.co`

5. **Abre ese email** y:
   - Haz clic en el enlace "Accept the invite"
   - Te llevará a una página para crear contraseña
   - **CREA ESTA CONTRASEÑA:** `VidaRelax2024!Admin`
   - Confirma la contraseña
   - Haz clic en "Create account"

6. **¡Listo!** Este usuario ya tiene acceso.

---

### Usuario 2: lastradanieleduardo@gmail.com (DANIEL - EL CLIENTE)

1. En Netlify, ve a: **Site configuration** → **Identity** → **"Invite users"**

2. Ingresa el email: `lastradanieleduardo@gmail.com`

3. Haz clic en **"Send invitation"**

4. **IMPORTANTE:** Daniel recibirá un email en `lastradanieleduardo@gmail.com`

5. **DILE A DANIEL QUE:**
   - Revise su email (también la carpeta de spam)
   - Haga clic en "Accept the invite"
   - Cree su propia contraseña (mínimo 8 caracteres)
   - Confirme la contraseña
   - Haga clic en "Create account"

---

## 🎯 PASO 4: VERIFICAR QUE FUNCIONA

### Para verificar el acceso administrativo:

1. **Ve a tu sitio:** `https://vidarelax.com.co/admin/`

2. **Haz clic en "Login with Netlify Identity"**

3. **Ingresa las credenciales:**
   - Email: `contactanos@vidarelax.com.co`
   - Contraseña: `VidaRelax2024!Admin`

4. **¡Deberías entrar al panel administrativo!** 🎉

5. **Verifica que puedes:**
   - Ver las colecciones (Configuración General, Junta Directiva, etc.)
   - Editar contenido
   - Subir archivos

---

## ⚠️ IMPORTANTE: CONFIGURAR VERCEL PARA NETLIFY IDENTITY

Como el sitio está en Vercel pero Identity está en Netlify, necesitamos configurar las URLs correctas:

1. **En Netlify Identity settings:**

   a) Ve a: **Site configuration** → **Identity** → **Settings**

   b) En **"External providers"**, busca **"Site URL"**

   c) Agrega tu dominio de Vercel: `https://vidarelax.com.co`

   d) Guarda los cambios

2. **Configurar Git Gateway para el dominio correcto:**

   En el mismo lugar, en **"Git Gateway"**, verifica que:
   - El repositorio conectado sea: `nicolas2456/Fundacion-VIDARELAX`
   - Branch: `main`

---

## 🔄 FLUJO DE LOGIN PARA LOS USUARIOS

### Para TI (contactanos@vidarelax.com.co):

1. Ve a: `https://vidarelax.com.co/admin/`
2. Haz clic en "Login with Netlify Identity"
3. Email: `contactanos@vidarelax.com.co`
4. Contraseña: `VidaRelax2024!Admin`
5. ¡Entra al panel!

### Para DANIEL (lastradanieleduardo@gmail.com):

1. Va a: `https://vidarelax.com.co/admin/`
2. Hace clic en "Login with Netlify Identity"
3. Email: `lastradanieleduardo@gmail.com`
4. Contraseña: La que él creó al aceptar la invitación
5. ¡Entra al panel!

---

## 📱 QUÉ PUEDEN EDITAR DESDE EL PANEL ADMIN:

Los usuarios podrán editar:

### ⚙️ Configuración General
- Nombre de la fundación
- NIT
- Eslogan
- Logo
- Fecha de constitución

### 🎯 Misión, Visión y Valores
- Textos completos
- Iconos

### 👥 Junta Directiva
- Agregar/eliminar miembros
- Cambiar fotos
- Editar cargos y datos

### 🏥 Servicios
- Agregar nuevos servicios
- Editar descripciones
- Cambiar iconos
- Reordenar

### 📄 Documentos Institucionales
- Subir nuevos PDFs
- Eliminar documentos
- Editar nombres y descripciones

### 💝 Información de Donaciones
- Agregar cuentas bancarias
- Editar textos de voluntariado/alianzas

### 📞 Información de Contacto
- Actualizar dirección
- Cambiar teléfonos
- Editar redes sociales
- Actualizar mapa de Google

### 🎨 Colores del Sitio
- Cambiar paleta de colores
- Modificar colores institucionales

---

## 🚨 TROUBLESHOOTING (SI ALGO NO FUNCIONA)

### Error: "Git Gateway is not enabled"

**Solución:**
1. Ve a Netlify → Site configuration → Identity
2. Haz clic en "Enable Git Gateway"
3. Espera 2-3 minutos
4. Intenta de nuevo

### Error: "Failed to load config.yml"

**Solución:**
1. Verifica que el archivo `/admin/config.yml` existe en el repositorio
2. Haz un push a main si falta
3. Espera a que Vercel se despliegue

### Error: "Unable to access API"

**Solución:**
1. Verifica que la URL del sitio en Netlify Identity settings sea: `https://vidarelax.com.co`
2. Verifica que Git Gateway esté habilitado
3. Verifica que el repositorio conectado sea el correcto

### El usuario no recibe el email de invitación

**Solución:**
1. Revisa la carpeta de spam
2. Reenvía la invitación desde Netlify
3. Verifica que el email esté escrito correctamente

---

## ✅ CHECKLIST FINAL

Marca cada paso cuando lo completes:

- [ ] Cuenta de Netlify creada
- [ ] Repositorio importado a Netlify
- [ ] Netlify Identity habilitado
- [ ] Git Gateway habilitado
- [ ] Usuario 1 invitado: contactanos@vidarelax.com.co
- [ ] Usuario 1 activó su cuenta (contraseña: VidaRelax2024!Admin)
- [ ] Usuario 2 invitado: lastradanieleduardo@gmail.com
- [ ] Usuario 2 recibió el email de invitación
- [ ] Site URL configurada en Netlify: https://vidarelax.com.co
- [ ] Probado el login en: https://vidarelax.com.co/admin/
- [ ] Verificado que se puede editar contenido

---

## 📞 SOPORTE

Si tienes algún problema:

1. Verifica que hayas seguido TODOS los pasos en orden
2. Revisa la sección de Troubleshooting
3. Verifica en Netlify Identity que ambos usuarios estén en la lista
4. Comprueba que Git Gateway esté activo (ícono verde)

---

## 🎉 ¡LISTO!

Una vez completados todos los pasos, tanto tú como Daniel podrán:

1. Entrar a `https://vidarelax.com.co/admin/`
2. Hacer login con sus respectivos emails
3. Editar TODO el contenido del sitio
4. Los cambios se guardarán automáticamente en GitHub
5. Vercel desplegará los cambios automáticamente

**¡El panel administrativo está 100% funcional!** 🚀
