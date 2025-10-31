# 🏥 Fundación Refugio Casa Vida Relax - VIDARELAX

**"Refugio para el cuerpo, alivio para el alma"**

Sitio web oficial de la Fundación Refugio Casa Vida Relax, albergue oncológico en Bucaramanga que brinda alojamiento digno y acompañamiento integral a pacientes oncológicos y sus familias.

---

## 📋 Tabla de Contenidos

- [Características del Sitio](#-características-del-sitio)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Despliegue en Netlify](#-despliegue-en-netlify)
- [Configuración de Netlify Identity](#-configuración-de-netlify-identity)
- [Acceso al Panel Administrativo](#-acceso-al-panel-administrativo)
- [Gestión de Contenidos](#-gestión-de-contenidos)
- [Conectar Dominio Personalizado](#-conectar-dominio-personalizado)
- [Solución de Problemas](#-solución-de-problemas)
- [Mantenimiento y Actualizaciones](#-mantenimiento-y-actualizaciones)
- [Soporte Técnico](#-soporte-técnico)

---

## ✨ Características del Sitio

### 🎨 Diseño y Experiencia
- ✅ Diseño responsive (móvil, tablet, desktop)
- ✅ Animaciones suaves y modernas
- ✅ Paleta de colores institucionales (Turquesa, Lavanda, Dorado)
- ✅ Tipografía profesional (Montserrat + Open Sans)
- ✅ Botón flotante de WhatsApp

### ⚙️ Funcionalidades Técnicas
- ✅ **Formulario de contacto funcional** con Netlify Forms
- ✅ **Panel administrativo completo** con Netlify CMS
- ✅ **Gestión de documentos PDF** descargables
- ✅ **Sistema de autenticación** con Netlify Identity
- ✅ **Optimización automática** de imágenes y assets
- ✅ **SSL automático** (HTTPS)
- ✅ **Headers de seguridad** configurados

### 📝 Contenidos Editables desde el Panel Admin
- Información general de la fundación
- Misión, Visión y Valores
- Junta Directiva (fotos, nombres, cargos)
- Servicios ofrecidos
- Documentos PDF institucionales
- Información bancaria para donaciones
- Datos de contacto y redes sociales
- Colores institucionales

---

## 📁 Estructura del Proyecto

```
fundacion-vidarelax/
├── 📄 index.html                 # Página principal del sitio
├── 📄 README.md                  # Este archivo de instrucciones
├── 📄 netlify.toml               # Configuración de Netlify
├── 📄 _redirects                 # Redirects y rewrites
│
├── 📁 admin/                     # Panel administrativo (Netlify CMS)
│   ├── 📄 index.html             # Interfaz del CMS
│   └── 📄 config.yml             # Configuración del CMS
│
├── 📁 _data/                     # Datos editables desde el CMS
│   ├── 📄 general.json           # Información general
│   ├── 📄 identidad.json         # Misión, Visión, Valores
│   ├── 📄 contacto.json          # Datos de contacto
│   ├── 📄 donaciones.json        # Info de donaciones y voluntariado
│   ├── 📄 estilos.json           # Colores institucionales
│   ├── 📁 junta/                 # Miembros de la junta directiva
│   ├── 📁 servicios/             # Servicios ofrecidos
│   └── 📁 documentos/            # Referencias a PDFs
│
├── 📁 documentos/                # Archivos PDF institucionales
│   └── 📄 .gitkeep
│
└── 📁 assets/                    # Archivos multimedia
    └── 📁 uploads/               # Imágenes y archivos subidos desde el CMS
        └── 📄 .gitkeep
```

---

## 🚀 Despliegue en Netlify

### **Paso 1: Subir el Código a GitHub**

1. **Crear un repositorio en GitHub:**
   - Ve a [github.com](https://github.com) e inicia sesión
   - Haz clic en el botón `+` (arriba a la derecha) → **New repository**
   - Nombre del repositorio: `fundacion-vidarelax-website` (o el que prefieras)
   - Visibilidad: **Public** (recomendado) o **Private**
   - **NO** marques "Initialize with README" (ya tienes este README)
   - Haz clic en **Create repository**

2. **Subir el código desde tu computadora:**

   ```bash
   # Navega a la carpeta del proyecto
   cd ruta/a/fundacion-vidarelax

   # Inicializar Git (si no está inicializado)
   git init

   # Agregar todos los archivos
   git add .

   # Crear el primer commit
   git commit -m "Sitio web inicial de Fundación VIDARELAX con Netlify CMS"

   # Conectar con tu repositorio de GitHub (reemplaza con tu URL)
   git remote add origin https://github.com/TU-USUARIO/fundacion-vidarelax-website.git

   # Subir a GitHub
   git branch -M main
   git push -u origin main
   ```

### **Paso 2: Conectar con Netlify**

1. **Crear cuenta en Netlify:**
   - Ve a [netlify.com](https://netlify.com)
   - Haz clic en **Sign up** (si no tienes cuenta)
   - Regístrate con tu cuenta de GitHub (recomendado)

2. **Importar el sitio:**
   - En el dashboard de Netlify, haz clic en **Add new site** → **Import an existing project**
   - Selecciona **Deploy with GitHub**
   - Autoriza a Netlify para acceder a tu cuenta de GitHub
   - Selecciona el repositorio `fundacion-vidarelax-website`

3. **Configurar el despliegue:**
   - **Branch to deploy:** `main`
   - **Build command:** (dejar vacío)
   - **Publish directory:** `.` (punto)
   - Haz clic en **Deploy site**

4. **Esperar el despliegue:**
   - Netlify comenzará a construir y desplegar tu sitio
   - Esto tomará 1-2 minutos
   - Una vez completado, verás un mensaje de **Published** ✅

5. **Tu sitio está en línea:**
   - Netlify te asignará una URL temporal como: `https://random-name-123456.netlify.app`
   - Puedes visitar esta URL para ver tu sitio funcionando

### **Paso 3: Cambiar el Nombre del Sitio (Opcional)**

1. En el dashboard de tu sitio en Netlify
2. Ve a **Site settings** → **General** → **Site details**
3. Haz clic en **Change site name**
4. Ingresa un nombre personalizado, por ejemplo: `vidarelax` o `fundacion-vidarelax`
5. Tu URL será: `https://vidarelax.netlify.app`

---

## 🔐 Configuración de Netlify Identity

Para que el panel administrativo (`/admin`) funcione, debes habilitar **Netlify Identity**:

### **Paso 1: Habilitar Identity**

1. En el dashboard de Netlify, ve a tu sitio
2. Haz clic en **Identity** (en el menú superior)
3. Haz clic en **Enable Identity**

### **Paso 2: Configurar Git Gateway**

1. En la misma página de **Identity**, baja hasta **Services**
2. Haz clic en **Enable Git Gateway**
3. Esto permite que el CMS guarde cambios directamente en GitHub

### **Paso 3: Configurar Registro de Usuarios**

1. Ve a **Identity** → **Settings and usage**
2. En **Registration preferences**, selecciona:
   - **Invite only** (Solo por invitación) ← **Recomendado para seguridad**
3. En **External providers** (opcional):
   - Puedes habilitar login con Google, GitHub, etc.

### **Paso 4: Invitar al Primer Usuario Administrativo**

1. Ve a **Identity** → **Invite users**
2. Ingresa el correo electrónico del administrador
3. Haz clic en **Send**
4. El administrador recibirá un correo con un enlace de invitación
5. Al hacer clic, podrá crear su contraseña

---

## 🖥️ Acceso al Panel Administrativo

### **Método 1: Desde el Sitio Web**

1. Visita tu sitio: `https://tu-sitio.netlify.app`
2. Haz clic en el botón **"Acceso Administrativo"** (arriba a la derecha)
3. Serás redirigido a: `https://tu-sitio.netlify.app/admin`
4. Inicia sesión con tu correo y contraseña (configurados en Identity)

### **Método 2: Acceso Directo**

1. Ve directamente a: `https://tu-sitio.netlify.app/admin`
2. Inicia sesión con tus credenciales

### **Primera Vez Ingresando:**

1. Si es tu primera vez, usa el enlace de invitación que recibiste por correo
2. Crea una contraseña segura
3. Confirma tu cuenta
4. Ya podrás acceder al panel administrativo

---

## 📝 Gestión de Contenidos

Una vez dentro del panel administrativo (`/admin`), puedes editar:

### **⚙️ Configuración General**
- Nombre de la fundación
- NIT
- Logo (URL)
- Eslogan
- Fecha de constitución

### **🎯 Misión, Visión y Valores**
- Editar textos completos
- Cambiar iconos (usando Font Awesome)

### **👥 Junta Directiva**
- Agregar/Eliminar miembros
- Subir fotos (o usar ícono predeterminado)
- Editar nombres, cargos, cédulas

### **🏥 Servicios Ofrecidos**
- Agregar nuevos servicios
- Editar descripciones
- Cambiar iconos y orden de aparición

### **📄 Documentos Institucionales**
- Subir archivos PDF
- Editar nombres y descripciones
- Eliminar documentos obsoletos

### **💝 Cómo Ayudar**
- Actualizar información bancaria
- Editar textos de donaciones, voluntariado y alianzas

### **📞 Información de Contacto**
- Dirección física
- Teléfonos
- Correo electrónico
- Redes sociales

### **🎨 Colores Institucionales**
- Modificar la paleta de colores del sitio (en formato hexadecimal)

### **Guardar Cambios:**

1. Haz clic en el contenido que deseas editar
2. Realiza las modificaciones
3. Haz clic en **Publish** o **Save** (arriba a la derecha)
4. Los cambios se guardarán automáticamente en GitHub
5. Netlify re-desplegará el sitio automáticamente (1-2 minutos)

---

## 🌐 Conectar Dominio Personalizado

Si tienes un dominio (ej: `vidarelax.com.co`), puedes conectarlo a Netlify:

### **Paso 1: Agregar el Dominio en Netlify**

1. En el dashboard de Netlify, ve a tu sitio
2. **Site settings** → **Domain management**
3. Haz clic en **Add custom domain**
4. Ingresa tu dominio: `vidarelax.com.co`
5. Haz clic en **Verify**

### **Paso 2: Configurar DNS**

Netlify te mostrará instrucciones específicas. Hay dos opciones:

#### **Opción A: Usar Netlify DNS (Recomendado - Más Fácil)**

1. Netlify te dará **nameservers** como:
   ```
   dns1.p03.nsone.net
   dns2.p03.nsone.net
   dns3.p03.nsone.net
   dns4.p03.nsone.net
   ```

2. Ve al sitio donde compraste tu dominio (ej: mi.com.co, GoDaddy, Namecheap)
3. Busca la sección **DNS** o **Nameservers**
4. Reemplaza los nameservers actuales por los de Netlify
5. Guarda los cambios
6. **Espera 24-48 horas** (propagación DNS)

#### **Opción B: Usar DNS de tu Proveedor Actual**

1. En tu proveedor de dominio, agrega un registro **A** apuntando a:
   ```
   75.2.60.5
   ```

2. Agrega un registro **CNAME** para `www` apuntando a:
   ```
   tu-sitio.netlify.app
   ```

3. Guarda los cambios
4. **Espera 1-24 horas** (propagación DNS)

### **Paso 3: Habilitar HTTPS**

1. Una vez conectado el dominio, Netlify habilitará automáticamente **HTTPS**
2. Esto puede tomar algunos minutos
3. Una vez listo, tu sitio será accesible como: `https://vidarelax.com.co` 🔒

---

## 🔧 Solución de Problemas

### **❌ El formulario de contacto no funciona**

**Problema:** Al enviar el formulario, no pasa nada o muestra error.

**Solución:**
1. Asegúrate de que el sitio esté desplegado en Netlify (no funcionará en localhost)
2. Verifica que el formulario tenga el atributo `data-netlify="true"`
3. En Netlify, ve a **Forms** en el dashboard para ver las sumisiones

### **❌ No puedo acceder a `/admin`**

**Problema:** La página `/admin` muestra "Not Found" o "Page not found".

**Solución:**
1. Verifica que Netlify Identity esté habilitado (ver sección anterior)
2. Verifica que Git Gateway esté habilitado
3. Limpia el caché del navegador (`Ctrl + Shift + R`)
4. Verifica que el archivo `admin/index.html` exista en tu repositorio

### **❌ No puedo iniciar sesión en `/admin`**

**Problema:** No aparece el formulario de login o muestra error.

**Solución:**
1. Asegúrate de haber recibido y completado el correo de invitación
2. Ve a Netlify → **Identity** → **Users** y verifica que tu usuario esté activo
3. Haz clic en **Resend invite** si no recibiste el correo
4. Revisa tu carpeta de spam

### **❌ Los cambios desde `/admin` no se guardan**

**Problema:** Edito el contenido pero no se refleja en el sitio.

**Solución:**
1. Verifica que Git Gateway esté habilitado en Netlify Identity
2. Asegúrate de hacer clic en **Publish** (no solo Save)
3. Espera 2-3 minutos para que Netlify re-despliegue el sitio
4. Limpia el caché del navegador

### **❌ Las imágenes no cargan**

**Problema:** Imágenes rotas o que no se muestran.

**Solución:**
1. Verifica que las URLs de las imágenes sean correctas
2. Si subes imágenes desde el CMS, asegúrate de que se guarden en `assets/uploads/`
3. Verifica que la carpeta `assets/uploads/` exista en GitHub

### **❌ El dominio personalizado no funciona**

**Problema:** El dominio muestra error o no carga el sitio.

**Solución:**
1. Verifica que los nameservers o registros DNS estén configurados correctamente
2. Espera al menos 24 horas (propagación DNS puede tomar tiempo)
3. Usa [DNS Checker](https://dnschecker.org) para verificar la propagación
4. En Netlify, ve a **Domain settings** y verifica que el dominio esté verificado

### **❌ Error 404 en algunas páginas**

**Problema:** Algunas rutas muestran error 404.

**Solución:**
1. Verifica que el archivo `_redirects` esté en la raíz del proyecto
2. Verifica que `netlify.toml` tenga las configuraciones de redirects
3. Re-despliega el sitio en Netlify

---

## 🛠️ Mantenimiento y Actualizaciones

### **Actualizar el Sitio desde GitHub:**

1. Clona el repositorio en tu computadora:
   ```bash
   git clone https://github.com/TU-USUARIO/fundacion-vidarelax-website.git
   cd fundacion-vidarelax-website
   ```

2. Realiza los cambios en el código

3. Guarda y sube los cambios:
   ```bash
   git add .
   git commit -m "Descripción de los cambios"
   git push origin main
   ```

4. Netlify detectará los cambios automáticamente y re-desplegará el sitio

### **Backup de Contenidos:**

- Todos los contenidos se guardan en GitHub automáticamente
- Para hacer un backup manual:
  1. Ve a tu repositorio en GitHub
  2. Haz clic en **Code** → **Download ZIP**
  3. Guarda el archivo ZIP en un lugar seguro

### **Revisar Logs de Despliegue:**

1. En Netlify, ve a tu sitio
2. Haz clic en **Deploys**
3. Selecciona el deploy más reciente
4. Haz clic en **Deploy log** para ver detalles

---

## 📞 Soporte Técnico

### **Recursos de Ayuda:**

- **Documentación de Netlify:** [docs.netlify.com](https://docs.netlify.com)
- **Documentación de Netlify CMS:** [netlifycms.org/docs](https://www.netlifycms.org/docs/)
- **Comunidad de Netlify:** [answers.netlify.com](https://answers.netlify.com)

### **Contacto de la Fundación:**

- **Email:** cvidarelax@gmail.com
- **Teléfono:** +57 (314) 817 9078
- **WhatsApp:** [Enviar mensaje](https://wa.me/573148179078)

---

## 📄 Licencia

Este sitio web es propiedad de la **Fundación Refugio Casa Vida Relax (VIDARELAX)**.

- **NIT:** 901.999.007-7
- **Constituida:** 6 de octubre de 2025
- **Ubicación:** Bucaramanga, Santander, Colombia

Todos los derechos reservados © 2025

---

## ✅ Checklist de Deployment

- [ ] Código subido a GitHub
- [ ] Sitio conectado con Netlify
- [ ] Sitio desplegado correctamente
- [ ] Netlify Identity habilitado
- [ ] Git Gateway habilitado
- [ ] Primer usuario administrativo invitado
- [ ] Acceso a `/admin` funcionando
- [ ] Formulario de contacto probado
- [ ] Contenidos editados desde el CMS
- [ ] Dominio personalizado conectado (si aplica)
- [ ] HTTPS habilitado
- [ ] Backup del código realizado

---

**¡Felicidades! 🎉 Tu sitio web está completamente funcional y listo para ayudar a transformar vidas.**

*"Refugio para el cuerpo, alivio para el alma"*
