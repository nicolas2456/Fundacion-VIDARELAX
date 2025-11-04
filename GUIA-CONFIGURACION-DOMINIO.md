# Guía de Configuración del Dominio vidarelax.com.co

## Información General

- **Dominio:** vidarelax.com.co
- **Proveedor del dominio:** m.icom.co
- **Plataforma de hosting:** Vercel
- **Sitio actual:** [URL temporal de Vercel - verificar en dashboard]

---

## PARTE 1: Configurar el Dominio en Vercel

### Paso 1: Acceder al Dashboard de Vercel

1. Ir a: https://vercel.com
2. Iniciar sesión con la cuenta del proyecto
3. Seleccionar el proyecto: **Fundacion-VIDARELAX**

### Paso 2: Agregar el Dominio

1. En el proyecto, ir a: **Settings** → **Domains**
2. Click en **Add Domain**
3. Escribir: `vidarelax.com.co`
4. Click en **Add**

### Paso 3: También agregar WWW (recomendado)

1. Repetir el proceso agregando: `www.vidarelax.com.co`
2. Vercel te preguntará si quieres redirigir `www` → `vidarelax.com.co` o viceversa
3. **Recomendación:** Redirigir `www.vidarelax.com.co` → `vidarelax.com.co`

### Paso 4: Obtener los Registros DNS

Después de agregar el dominio, Vercel te mostrará los registros DNS necesarios:

**Para vidarelax.com.co:**
```
Tipo: A
Nombre: @ (o dejar vacío)
Valor: 76.76.21.21
TTL: 3600 (o automático)
```

**Para www.vidarelax.com.co:**
```
Tipo: CNAME
Nombre: www
Valor: cname.vercel-dns.com
TTL: 3600 (o automático)
```

**IMPORTANTE:** Copia estos valores exactos que te muestre Vercel, pueden variar.

---

## PARTE 2: Configurar DNS en m.icom.co

### Paso 1: Acceder al Panel de m.icom.co

1. Ir a: https://m.icom.co (o el panel de cliente que te hayan dado)
2. Iniciar sesión con tus credenciales
3. Buscar la sección: **Mis Dominios** o **Gestión de Dominios**
4. Seleccionar: **vidarelax.com.co**

### Paso 2: Acceder a la Configuración DNS

1. Buscar opciones como:
   - **DNS Settings**
   - **Administrar DNS**
   - **Zona DNS**
   - **Name Servers**

### Paso 3: Configurar los Registros DNS

**Antes de agregar, ELIMINA estos registros si existen:**
- Cualquier registro A que apunte a @ o al dominio raíz
- Cualquier registro CNAME con nombre @ o www que ya existan

**Ahora AGREGA estos registros nuevos:**

#### Registro A (dominio principal):
```
Tipo: A
Host/Nombre: @ (o vidarelax.com.co o dejar vacío, según el panel)
Valor/Apunta a: 76.76.21.21
TTL: 3600 (o Automático)
```

#### Registro CNAME (www):
```
Tipo: CNAME
Host/Nombre: www
Valor/Apunta a: cname.vercel-dns.com
TTL: 3600 (o Automático)
```

### Paso 4: Guardar los Cambios

1. Click en **Guardar** o **Save Changes**
2. Confirma los cambios si te pide confirmación

---

## PARTE 3: Verificación y Tiempos de Propagación

### Tiempos Estimados

- **Mínimo:** 5-10 minutos
- **Normal:** 1-4 horas
- **Máximo:** 24-48 horas (raro)

### Verificar la Configuración

#### Opción 1: Desde Vercel

1. Volver a Vercel → Settings → Domains
2. Verás el estado del dominio:
   - ⏳ **Pending:** Esperando propagación DNS
   - ✅ **Valid:** ¡Configurado correctamente!
   - ❌ **Invalid:** Revisar configuración DNS

#### Opción 2: Herramientas Online

**Verificar registros DNS:**
- https://dnschecker.org
  - Buscar: `vidarelax.com.co`
  - Tipo: `A`
  - Debería mostrar: `76.76.21.21`

- https://dnschecker.org
  - Buscar: `www.vidarelax.com.co`
  - Tipo: `CNAME`
  - Debería mostrar: `cname.vercel-dns.com`

#### Opción 3: Desde Terminal (si sabes usar comandos)

```bash
# Verificar registro A
dig vidarelax.com.co A

# Verificar registro CNAME
dig www.vidarelax.com.co CNAME
```

---

## PARTE 4: Configurar SSL/HTTPS (Automático)

Vercel configura SSL automáticamente usando Let's Encrypt.

**Esto sucede automáticamente cuando:**
1. Los registros DNS estén correctos
2. El dominio esté verificado en Vercel

**Tiempo estimado para SSL:** 1-10 minutos después de que DNS esté propagado

**Verificar SSL:**
1. Ir a: `https://vidarelax.com.co`
2. Debe mostrar el candado 🔒 en la barra del navegador
3. Certificado válido emitido por Let's Encrypt

---

## CHECKLIST COMPLETO

### En Vercel:
- [ ] Agregar dominio: `vidarelax.com.co`
- [ ] Agregar dominio: `www.vidarelax.com.co`
- [ ] Configurar redirect: `www` → dominio principal
- [ ] Copiar valores exactos de registros DNS

### En m.icom.co:
- [ ] Acceder al panel de DNS
- [ ] Eliminar registros A y CNAME existentes (si hay)
- [ ] Agregar registro A: `@ → 76.76.21.21`
- [ ] Agregar registro CNAME: `www → cname.vercel-dns.com`
- [ ] Guardar cambios

### Verificación:
- [ ] Esperar 1-4 horas para propagación DNS
- [ ] Verificar en dnschecker.org
- [ ] Ver estado en Vercel Domains (debe decir "Valid")
- [ ] Probar `https://vidarelax.com.co` en navegador
- [ ] Probar `https://www.vidarelax.com.co` (debe redirigir)
- [ ] Verificar SSL activo (candado 🔒)

---

## PROBLEMAS COMUNES Y SOLUCIONES

### ❌ Problema: "Domain is not configured correctly"

**Solución:**
- Verificar que los registros DNS estén exactos
- Esperar más tiempo (hasta 48 horas máximo)
- Verificar en dnschecker.org que los DNS estén propagados

### ❌ Problema: "SSL Certificate Error"

**Solución:**
- Esperar 10-30 minutos más
- El SSL se genera después de que DNS esté propagado
- Si persiste después de 1 hora, contactar soporte de Vercel

### ❌ Problema: "www no redirige al dominio principal"

**Solución:**
- Verificar que el registro CNAME de www esté correcto
- En Vercel Settings → Domains, verificar la configuración de redirect

### ❌ Problema: "m.icom.co no me deja modificar DNS"

**Solución:**
- Verificar que los Name Servers del dominio NO estén delegados a otro proveedor
- Si están usando Name Servers de otro proveedor, debes configurar DNS allá
- Contactar soporte de m.icom.co si no tienes acceso

---

## INFORMACIÓN DE SOPORTE

**Vercel:**
- Documentación: https://vercel.com/docs/projects/domains
- Soporte: https://vercel.com/support

**m.icom.co:**
- Soporte: [Agregar email/teléfono de soporte m.icom.co]

---

## VALORES DE REFERENCIA RÁPIDA

**Registros DNS a configurar en m.icom.co:**

| Tipo | Host/Nombre | Valor | TTL |
|------|-------------|-------|-----|
| A | @ | 76.76.21.21 | 3600 |
| CNAME | www | cname.vercel-dns.com | 3600 |

**NOTA:** Los valores IP pueden cambiar. Siempre usar los valores exactos que Vercel muestre en su panel.

---

## SIGUIENTE PASO DESPUÉS DE CONECTAR DOMINIO

Una vez el dominio esté funcionando:

1. Actualizar enlaces en redes sociales
2. Actualizar información de contacto en documentos
3. Configurar correos corporativos @vidarelax.com.co (si decides comprarlos)
4. Configurar Web3Forms con los correos definitivos
5. Solicitar indexación en Google Search Console

---

**Fecha de creación:** 2025-11-04
**Última actualización:** 2025-11-04
