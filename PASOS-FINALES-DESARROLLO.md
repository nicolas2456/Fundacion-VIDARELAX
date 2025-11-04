# Pasos Finales - Cuando el Cliente Envíe los Access Keys
## Guía para el desarrollador

---

## Situación Actual

✅ **Completado:**
- Sistema de 4 formularios implementado
- PDFs creados y disponibles
- Dominio vidarelax.com.co conectado
- Sitio en producción

⏳ **Pendiente:**
- Actualizar 4 Access Keys de Web3Forms en el código
- Deploy final a producción

---

## Cuando Recibas los Access Keys

El cliente debe enviarte:

```
Access Key 1 - Contacto General: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Access Key 2 - Voluntariado: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Access Key 3 - Donaciones: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Access Key 4 - Alianzas: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

---

## PASO 1: Actualizar Access Keys en index.html

### Ubicaciones exactas:

**Formulario 1 - Contacto General:**
- **Archivo:** `index.html`
- **Línea aproximada:** ~2259
- **Buscar:** `YOUR_WEB3FORMS_ACCESS_KEY_GENERAL`
- **Reemplazar con:** Access Key 1

**Formulario 2 - Voluntariado:**
- **Archivo:** `index.html`
- **Línea aproximada:** ~2313
- **Buscar:** `YOUR_WEB3FORMS_ACCESS_KEY_VOLUNTARIADO`
- **Reemplazar con:** Access Key 2

**Formulario 3 - Donaciones:**
- **Archivo:** `index.html`
- **Línea aproximada:** ~2459
- **Buscar:** `YOUR_WEB3FORMS_ACCESS_KEY_DONACIONES`
- **Reemplazar con:** Access Key 3

**Formulario 4 - Alianzas:**
- **Archivo:** `index.html`
- **Línea aproximada:** ~2604
- **Buscar:** `YOUR_WEB3FORMS_ACCESS_KEY_ALIANZAS`
- **Reemplazar con:** Access Key 4

---

## PASO 2: Búsqueda y Reemplazo (método rápido)

### Opción A - Buscar y reemplazar manualmente:

1. Abrir `index.html`
2. Buscar (Ctrl+F): `YOUR_WEB3FORMS_ACCESS_KEY_GENERAL`
3. Reemplazar con: [Access Key 1 del cliente]
4. Repetir para los otros 3 placeholders

### Opción B - Usando grep para verificar:

```bash
# Verificar que existen los placeholders
grep -n "YOUR_WEB3FORMS_ACCESS_KEY" index.html

# Debe mostrar 4 líneas
```

### Opción C - Sed para reemplazar (cuidado):

```bash
# ANTES de ejecutar, hacer backup
cp index.html index.html.backup

# Reemplazar (ajustar los Access Keys reales)
sed -i 's/YOUR_WEB3FORMS_ACCESS_KEY_GENERAL/a1b2c3d4-xxxx-xxxx-xxxx-xxxxxxxxxxxx/g' index.html
sed -i 's/YOUR_WEB3FORMS_ACCESS_KEY_VOLUNTARIADO/b2c3d4e5-xxxx-xxxx-xxxx-xxxxxxxxxxxx/g' index.html
sed -i 's/YOUR_WEB3FORMS_ACCESS_KEY_DONACIONES/c3d4e5f6-xxxx-xxxx-xxxx-xxxxxxxxxxxx/g' index.html
sed -i 's/YOUR_WEB3FORMS_ACCESS_KEY_ALIANZAS/d4e5f6a7-xxxx-xxxx-xxxx-xxxxxxxxxxxx/g' index.html

# Verificar que se reemplazaron
grep -n "YOUR_WEB3FORMS_ACCESS_KEY" index.html
# No debe mostrar nada
```

---

## PASO 3: Verificar los cambios

### Abrir index.html y verificar que se vean así:

**Línea ~2259:**
```html
<input type="hidden" name="access_key" value="a1b2c3d4-xxxx-xxxx-xxxx-xxxxxxxxxxxx">
```

**Línea ~2313:**
```html
<input type="hidden" name="access_key" value="b2c3d4e5-xxxx-xxxx-xxxx-xxxxxxxxxxxx">
```

**Línea ~2459:**
```html
<input type="hidden" name="access_key" value="c3d4e5f6-xxxx-xxxx-xxxx-xxxxxxxxxxxx">
```

**Línea ~2604:**
```html
<input type="hidden" name="access_key" value="d4e5f6a7-xxxx-xxxx-xxxx-xxxxxxxxxxxx">
```

**⚠️ IMPORTANTE:** Verificar que:
- Los 4 Access Keys son DIFERENTES entre sí
- No quedaron placeholders sin reemplazar
- No hay errores de sintaxis (comillas, espacios extra, etc.)

---

## PASO 4: Commit y Push

```bash
# Verificar cambios
git status
git diff index.html

# Agregar cambios
git add index.html

# Commit con mensaje descriptivo
git commit -m "Configurar Access Keys de Web3Forms para formularios

Actualizados los 4 Access Keys en los formularios:
- Contacto General
- Voluntariado
- Donaciones
- Alianzas Corporativas

Los formularios ahora enviarán mensajes a contactovidarelax@gmail.com
a través de Web3Forms (1,000 envíos/mes gratis por formulario)."

# Push a la rama actual
git push origin claude/vidarelax-domain-setup-011CUjW2XRMrXcbkihAjSJxX
```

---

## PASO 5: Merge a main (si todo está OK)

### Opción A - Crear Pull Request:

Si aún no has hecho el PR de todos los cambios acumulados:

```bash
# Ir a GitHub
https://github.com/nicolas2456/Fundacion-VIDARELAX/compare/main...claude/vidarelax-domain-setup-011CUjW2XRMrXcbkihAjSJxX

# Crear PR con título:
"Sistema completo de formularios + PDFs + Configuración de dominio"

# Merge el PR
```

### Opción B - Merge directo (si tienes permisos):

```bash
# Cambiar a main
git checkout main

# Pull para actualizar
git pull origin main

# Merge de la rama de desarrollo
git merge claude/vidarelax-domain-setup-011CUjW2XRMrXcbkihAjSJxX

# Push a main
git push origin main
```

---

## PASO 6: Verificar Deploy en Vercel

1. Ir a: https://vercel.com
2. Abrir proyecto: Fundacion-VIDARELAX
3. Ver que el deploy se ejecutó automáticamente
4. Esperar a que termine (1-2 minutos)
5. Ver que aparezca: ✅ **Ready** en el último deployment

---

## PASO 7: Probar los Formularios

### Test del Formulario de Contacto General:

1. Ir a: https://vidarelax.com.co
2. Scroll hasta la sección de Contacto
3. Click en la pestaña: **Contacto General**
4. Llenar el formulario:
   ```
   Nombre: Test Desarrollador
   Email: tu-email@ejemplo.com
   Teléfono: 3001234567
   Asunto: Consulta General
   Mensaje: Esto es una prueba del formulario
   ☑ Autorización
   ```
5. Click en **Enviar**
6. Debe mostrar mensaje de éxito
7. Verificar que llegó email a contactovidarelax@gmail.com

### Test de los otros 3 formularios:

Repetir el proceso para:
- Pestaña **Voluntariado**
- Pestaña **Donaciones**
- Pestaña **Alianzas**

**Verificar que:**
- ✅ Todos los formularios envían correctamente
- ✅ Llegan emails a contactovidarelax@gmail.com
- ✅ Los emails identifican claramente de qué formulario vienen
- ✅ Los campos condicionales funcionan (en Voluntariado y Donaciones)
- ✅ Las validaciones funcionan (campos requeridos, emails, etc.)

---

## PASO 8: Notificar al Cliente

Enviar mensaje:

```
Hola,

✅ ¡Todo listo! Los formularios ya están funcionando al 100%.

He actualizado el código con los Access Keys que me enviaste y todo
está en producción.

PRUEBAS REALIZADAS:
✅ Formulario de Contacto General - Funcionando
✅ Formulario de Voluntariado - Funcionando
✅ Formulario de Donaciones - Funcionando
✅ Formulario de Alianzas - Funcionando

Todos los mensajes llegarán a: contactovidarelax@gmail.com

PRÓXIMOS PASOS (opcional, cuando decidas):
• Actualizar datos en PDFs (NIT, cuenta bancaria, teléfonos reales)
• Considerar migración a correos corporativos @vidarelax.com.co
• Renovar dominio antes del 30/01/2025

El sitio está 100% funcional y listo para recibir contactos.

¡Felicidades! 🎉

Saludos,
[Tu nombre]
```

---

## Checklist Final

- [ ] Recibir los 4 Access Keys del cliente
- [ ] Actualizar index.html (4 reemplazos)
- [ ] Verificar que no quedaron placeholders
- [ ] Git add, commit, push
- [ ] Merge a main (o crear PR)
- [ ] Verificar deploy en Vercel
- [ ] Probar los 4 formularios en producción
- [ ] Verificar que llegan emails
- [ ] Notificar al cliente que está todo listo

---

## Tiempo Estimado

- Actualizar Access Keys: 5 minutos
- Commit y push: 2 minutos
- Merge y deploy: 5 minutos
- Pruebas: 10 minutos
- Notificación al cliente: 2 minutos

**Total: ~25 minutos**

---

## Comandos Rápidos (copiar/pegar)

```bash
# Verificar placeholders actuales
grep -n "YOUR_WEB3FORMS_ACCESS_KEY" index.html

# Después de reemplazar manualmente, verificar que no quedó ninguno
grep -n "YOUR_WEB3FORMS_ACCESS_KEY" index.html

# Si no muestra nada, está OK

# Git workflow
git add index.html
git commit -m "Configurar Access Keys de Web3Forms para formularios"
git push origin claude/vidarelax-domain-setup-011CUjW2XRMrXcbkihAjSJxX

# Probar formularios
# Ir a: https://vidarelax.com.co
# Probar cada uno y verificar emails
```

---

## Notas Importantes

1. **No commitear Access Keys de prueba:** Asegúrate de que los Access Keys sean los reales del cliente, no placeholders.

2. **Seguridad:** Los Access Keys no son super secretos (están en el código público del frontend), pero es buena práctica no compartirlos innecesariamente.

3. **Backup:** Si algo sale mal, puedes revertir con:
   ```bash
   git checkout HEAD -- index.html
   ```

4. **Emails de prueba:** Usa tu propio email al probar, no el del cliente, para no llenar su bandeja de entrada.

---

**Última actualización:** 2025-11-04
