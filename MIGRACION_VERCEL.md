# 🚀 Guía de Migración de Netlify a Vercel

Esta guía te ayudará a migrar la página web de Fundación VIDARELAX de Netlify a Vercel, manteniendo **TODAS las funcionalidades**.

---

## ✅ Cambios Realizados (Ya completados)

### 1. **Formulario de Contacto**
- ✅ Migrado de **Netlify Forms** a **Web3Forms**
- ✅ Sigue siendo gratuito (250 envíos/mes)
- ✅ Misma funcionalidad: envía a contactanos@vidarelax.com.co

### 2. **Panel Administrativo (CMS)**
- ✅ Actualizado de **Netlify CMS** a **Decap CMS**
- ✅ Funciona exactamente igual
- ✅ Ahora usa autenticación con GitHub OAuth

### 3. **Configuración de Hosting**
- ✅ Creado `vercel.json` para configuración de Vercel
- ✅ Optimizaciones de caché y seguridad incluidas

---

## 📋 Pasos para Completar la Migración

### **PASO 1: Obtener Access Key de Web3Forms** (2 minutos)

1. Ve a: **https://web3forms.com/**
2. Click en **"Get Started"** o **"Create Access Key"**
3. Ingresa tu email: **contactanos@vidarelax.com.co**
4. Recibirás un email con tu **Access Key** (una cadena alfanumérica)
5. **Guarda esa Access Key**, la necesitaremos en el Paso 4

---

### **PASO 2: Conectar el Repositorio a Vercel** (5 minutos)

1. **Crea una cuenta en Vercel** (si no tienes una):
   - Ve a: **https://vercel.com/signup**
   - Regístrate con tu cuenta de **GitHub**
   - Es totalmente **GRATIS** e **ILIMITADO**

2. **Importa el proyecto**:
   - En el dashboard de Vercel, click en **"Add New"** → **"Project"**
   - Busca el repositorio: **nicolas2456/Fundacion-VIDARELAX**
   - Click en **"Import"**

3. **Configura el proyecto**:
   - **Framework Preset**: Other (o déjalo en blanco)
   - **Root Directory**: `.` (punto)
   - **Build Command**: (déjalo vacío)
   - **Output Directory**: (déjalo vacío)
   - Click en **"Deploy"**

4. **Espera el despliegue**:
   - Vercel desplegará automáticamente (1-2 minutos)
   - Te dará una URL como: `https://fundacion-vidarelax.vercel.app`

---

### **PASO 3: Configurar Dominio Personalizado (Opcional)**

Si quieres usar un dominio como `www.vidarelax.com.co`:

1. En Vercel, ve a tu proyecto → **"Settings"** → **"Domains"**
2. Agrega tu dominio personalizado
3. Sigue las instrucciones para configurar los DNS

---

### **PASO 4: Configurar Web3Forms en el Código**

1. **Abre el archivo**: `index.html`

2. **Busca la línea 1093** (aproximadamente):
   ```html
   <input type="hidden" name="access_key" value="YOUR_WEB3FORMS_ACCESS_KEY">
   ```

3. **Reemplaza** `YOUR_WEB3FORMS_ACCESS_KEY` con tu Access Key del Paso 1:
   ```html
   <input type="hidden" name="access_key" value="TU-CLAVE-AQUI">
   ```

4. **Busca la línea 1099** y actualiza la URL de redirección:
   ```html
   <input type="hidden" name="redirect" value="https://TU-URL-DE-VERCEL.vercel.app/?success=true">
   ```
   Reemplaza con tu URL real de Vercel.

5. **Guarda** y haz **commit** y **push** a GitHub:
   ```bash
   git add index.html
   git commit -m "Configurar Web3Forms con Access Key"
   git push origin main
   ```

6. Vercel **desplegará automáticamente** los cambios en segundos.

---

### **PASO 5: Configurar GitHub OAuth para el CMS** (10 minutos)

Para que el panel administrativo (/admin) funcione, necesitas crear una GitHub OAuth App:

1. **Ve a GitHub Settings**:
   - Abre: https://github.com/settings/developers
   - Click en **"OAuth Apps"** → **"New OAuth App"**

2. **Completa el formulario**:
   - **Application name**: `Fundación VIDARELAX CMS`
   - **Homepage URL**: `https://TU-URL-DE-VERCEL.vercel.app`
   - **Authorization callback URL**: `https://api.netlify.com/auth/done`
     (Sí, usa esta URL de Netlify aunque estés en Vercel - Decap CMS la usa)
   - Click en **"Register application"**

3. **Copia las credenciales**:
   - Verás un **Client ID** (copialo)
   - Click en **"Generate a new client secret"**
   - Copia el **Client Secret** (solo se mostrará una vez)

4. **Configura Decap CMS**:
   - Ve a tu URL de Vercel: `https://TU-URL-DE-VERCEL.vercel.app/admin`
   - La primera vez te pedirá autenticación con GitHub
   - Usa las credenciales que acabas de crear

5. **IMPORTANTE**: El CMS ahora pedirá **login con GitHub** en lugar de Netlify Identity
   - Los 2 administradores deben tener acceso al repositorio de GitHub
   - Ve a tu repositorio → **Settings** → **Collaborators**
   - Agrega a los 2 administradores con permisos de **Write**

---

### **PASO 6: Probar Todo** (5 minutos)

✅ **Prueba el formulario de contacto**:
- Ve a la sección de contacto
- Llena el formulario
- Envíalo
- Deberías recibir el email en contactanos@vidarelax.com.co

✅ **Prueba el panel administrativo**:
- Ve a: `https://TU-URL-DE-VERCEL.vercel.app/admin`
- Inicia sesión con GitHub
- Edita algo (por ejemplo, un texto)
- Guarda los cambios
- Los cambios se subirán automáticamente a GitHub

✅ **Prueba las descargas de PDFs**:
- Ve a la sección "Transparencia"
- Click en cualquier documento
- Debería descargarse correctamente

---

## 🎉 ¡LISTO! Migración Completada

### Resumen de lo que tienes ahora:

| Funcionalidad | Antes (Netlify) | Ahora (Vercel) | Estado |
|---------------|-----------------|----------------|--------|
| Hosting | Netlify (100GB límite) | Vercel (Ilimitado) | ✅ Mejorado |
| Formulario | Netlify Forms | Web3Forms (250/mes) | ✅ Funcional |
| CMS | Netlify CMS | Decap CMS | ✅ Igual funcionalidad |
| Autenticación | Netlify Identity | GitHub OAuth | ✅ Funcional |
| Despliegue Auto | ✅ | ✅ | ✅ Mantenido |
| Costo | $0 (con límites) | $0 (sin límites) | ✅ Gratis ilimitado |

---

## 📞 Soporte

Si tienes algún problema durante la migración:
1. Revisa cada paso cuidadosamente
2. Verifica que todas las URLs estén actualizadas
3. Asegúrate de que los Access Keys sean correctos

---

## 🔄 Ventajas de Vercel sobre Netlify

- ✅ **Sin límites de bandwidth** (Netlify: 100GB/mes)
- ✅ **Despliegues ilimitados** (Netlify: limitados en plan gratuito)
- ✅ **Más rápido** (red global optimizada)
- ✅ **Mismo flujo de trabajo** (Git push → despliegue automático)
- ✅ **Completamente gratis** para proyectos como este

---

**¡Tu página web de Fundación VIDARELAX ahora está en una plataforma mejor y sin límites!** 🚀
