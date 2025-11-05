# ⚡ PASOS RÁPIDOS: Configurar Acceso Administrativo

## 🎯 OBJETIVO

Dar acceso administrativo a:
1. **contactanos@vidarelax.com.co** → Contraseña: `VidaRelax2024!Admin`
2. **lastradanieleduardo@gmail.com** → Daniel crea su propia contraseña

---

## 📝 PASO A PASO (15 MINUTOS)

### 1️⃣ CREAR CUENTA EN NETLIFY (5 min)

```
1. Ve a: https://app.netlify.com/signup
2. Regístrate con tu email
3. Confirma tu email
```

---

### 2️⃣ IMPORTAR REPOSITORIO (3 min)

```
1. En Netlify: "Add new site" → "Import an existing project"
2. Conecta con GitHub
3. Selecciona: nicolas2456/Fundacion-VIDARELAX
4. Build command: echo "No build needed"
5. Publish directory: .
6. Deploy site
```

⚠️ **NO USES ESTE SITIO** - Solo necesitamos Netlify para la autenticación

---

### 3️⃣ HABILITAR NETLIFY IDENTITY (2 min)

```
1. En Netlify dashboard → "Site configuration" → "Identity"
2. Clic en "Enable Identity"
3. Registration: "Invite only"
4. Clic en "Enable Git Gateway"
5. Rol: "Open to anyone with valid account"
```

---

### 4️⃣ CONFIGURAR SITE URL (1 min)

```
1. En Identity settings → "Settings" → "Site URL"
2. Agrega: https://vidarelax.com.co
3. Guarda
```

---

### 5️⃣ INVITAR USUARIO 1: contactanos@vidarelax.com.co (4 min)

```
1. En Identity → "Invite users"
2. Email: contactanos@vidarelax.com.co
3. "Send invitation"
4. Abre el email que llegó a contactanos@vidarelax.com.co
5. Clic en "Accept the invite"
6. Crear contraseña: VidaRelax2024!Admin
7. Confirmar contraseña
8. "Create account"
```

✅ **¡Usuario 1 listo!**

---

### 6️⃣ INVITAR USUARIO 2: lastradanieleduardo@gmail.com (1 min tuyo + tiempo de Daniel)

```
1. En Identity → "Invite users"
2. Email: lastradanieleduardo@gmail.com
3. "Send invitation"
4. DILE A DANIEL que revise su email y:
   - Haga clic en "Accept the invite"
   - Cree su propia contraseña
   - Confirme
```

✅ **¡Usuario 2 invitado!**

---

### 7️⃣ PROBAR QUE FUNCIONA (2 min)

```
1. Ve a: https://vidarelax.com.co/admin/
2. Clic en "Login with Netlify Identity"
3. Email: contactanos@vidarelax.com.co
4. Password: VidaRelax2024!Admin
5. ¡Deberías ver el panel administrativo!
```

🎉 **¡LISTO! Ambos usuarios tienen acceso**

---

## 📋 RESUMEN DE CREDENCIALES

### Usuario 1 (TÚ):
- **URL:** https://vidarelax.com.co/admin/
- **Email:** contactanos@vidarelax.com.co
- **Password:** VidaRelax2024!Admin
- ⚠️ **Cámbiala después del primer login**

### Usuario 2 (DANIEL):
- **URL:** https://vidarelax.com.co/admin/
- **Email:** lastradanieleduardo@gmail.com
- **Password:** La que él creó al aceptar la invitación

---

## ✅ CHECKLIST

- [ ] Cuenta Netlify creada
- [ ] Repo importado a Netlify
- [ ] Identity habilitado
- [ ] Git Gateway habilitado
- [ ] Site URL configurada: https://vidarelax.com.co
- [ ] Usuario 1 invitado y activado
- [ ] Usuario 2 invitado
- [ ] Probado login en /admin/

---

## 🚨 ERRORES COMUNES

**"Git Gateway is not enabled"**
→ Ve a Identity → Enable Git Gateway → Espera 2-3 min

**No recibe el email**
→ Revisa spam → Reenvía invitación desde Netlify

**"Failed to load config"**
→ Espera a que Vercel despliegue → Recarga la página

---

## 💡 INSTRUCCIONES DETALLADAS

Si necesitas más detalles, lee: `INSTRUCCIONES-ACCESO-ADMINISTRATIVO.md`

---

## 🎯 ¿QUÉ PUEDEN EDITAR?

Desde `/admin/` podrán editar:
- ⚙️ Configuración general
- 🎯 Misión, visión, valores
- 👥 Junta directiva
- 🏥 Servicios
- 📄 Documentos PDF
- 💝 Info de donaciones
- 📞 Contacto
- 🎨 Colores del sitio

**Todo sin tocar código** ✨
