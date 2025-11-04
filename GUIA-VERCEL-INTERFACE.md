# GUÍA RÁPIDA - Agregar vidarelax.com.co en Vercel
## Interfaz específica de Vercel 2025

---

## PASO 1: Agregar el dominio principal (vidarelax.com.co)

### 1.1 Abrir el modal de agregar dominio

En la vista de Domains (donde ya ves fundacion-vidarelax1.vercel.app):

1. Click en el botón **[Add Domain]** (esquina superior derecha)
2. Se abrirá el modal "Add Domain"

### 1.2 Completar el formulario

En el modal que aparece:

```
┌─────────────────────────────────────────────────┐
│              Add Domain                         │
│                                                 │
│ ┌─────────────────────────────────────────────┐│
│ │ 🔍  vidarelax.com.co                        ││ ← ESCRIBIR AQUÍ
│ └─────────────────────────────────────────────┘│
│                                                 │
│ ◉ Connect to an environment                    │  ← SELECCIONAR ESTA
│    ┌────────────────────┐                      │
│    │ 🎯 Production  ▼   │                      │  ← DEJAR EN Production
│    └────────────────────┘                      │
│                                                 │
│ ○ Redirect to Another Domain                   │  ← NO SELECCIONAR
│                                                 │
│         [Cancel]              [Save]           │
└─────────────────────────────────────────────────┘
```

**Llenar así:**
- **Campo de texto:** `vidarelax.com.co` (sin www, sin https://)
- **Opción seleccionada:** ◉ Connect to an environment (círculo lleno)
- **Dropdown:** 🎯 Production (dejar por defecto)
- **NO seleccionar** la opción "Redirect to Another Domain"

### 1.3 Guardar

1. Click en **[Save]**
2. Esperar 2-3 segundos

---

## PASO 2: Ver los valores DNS requeridos

Después de dar Save, Vercel te mostrará una pantalla con los DNS records necesarios.

### 2.1 Identificar el tipo de configuración

Vercel puede mostrarte 2 opciones diferentes:

**OPCIÓN A - Registros A (más común):**
```
┌─────────────────────────────────────────────────────────┐
│ Configure DNS for vidarelax.com.co                      │
│                                                          │
│ Add the following DNS records to your domain provider:  │
│                                                          │
│ Type   Name   Value                                     │
│ ────────────────────────────────────────────────────── │
│ A      @      76.76.21.21         [Copy] [Copied ✓]    │
│                                                          │
│ Invalid Configuration - Add DNS records shown above     │
└─────────────────────────────────────────────────────────┘
```

**OPCIÓN B - Registros CNAME (menos común para dominio raíz):**
```
┌─────────────────────────────────────────────────────────┐
│ Configure DNS for vidarelax.com.co                      │
│                                                          │
│ Type   Name   Value                                     │
│ ────────────────────────────────────────────────────── │
│ CNAME  @      cname.vercel-dns.com  [Copy] [Copied ✓] │
└─────────────────────────────────────────────────────────┘
```

### 2.2 Copiar los valores

**SI TE MUESTRA REGISTRO A:**
1. Click en el botón **[Copy]** junto al valor de la IP
2. **ANOTAR:** La IP (ejemplo: 76.76.21.21)

**SI TE MUESTRA CNAME:**
1. Click en **[Copy]** junto a cname.vercel-dns.com
2. **ANOTAR:** El valor del CNAME

**⚠️ IMPORTANTE:** Usa el valor EXACTO que Vercel te muestre, no el del ejemplo.

---

## PASO 3: Agregar el subdominio www

### 3.1 Volver a abrir Add Domain

1. Click nuevamente en **[Add Domain]**
2. Se abrirá el mismo modal

### 3.2 Completar para www

```
┌─────────────────────────────────────────────────┐
│              Add Domain                         │
│                                                 │
│ ┌─────────────────────────────────────────────┐│
│ │ 🔍  www.vidarelax.com.co                    ││ ← ESCRIBIR CON www
│ └─────────────────────────────────────────────┘│
│                                                 │
│ ○ Connect to an environment                    │
│                                                 │
│ ◉ Redirect to Another Domain                   │  ← SELECCIONAR ESTA
│    ┌────────────────┐  ┌──────────────────────┐│
│    │ 308 Permanent ▼│  │ vidarelax.com.co  ▼  ││ ← Vercel sugiere
│    │ Redirect       │  │                       ││   automáticamente
│    └────────────────┘  └──────────────────────┘│
│                                                 │
│         [Cancel]              [Save]           │
└─────────────────────────────────────────────────┘
```

**Llenar así:**
- **Campo de texto:** `www.vidarelax.com.co`
- **Opción seleccionada:** ◉ Redirect to Another Domain
- **Tipo de redirect:** 308 Permanent Redirect (por defecto)
- **Redirect to:** vidarelax.com.co (Vercel lo sugiere automáticamente)

**¿Por qué esto?** Para que www.vidarelax.com.co redirija automáticamente a vidarelax.com.co

### 3.3 Guardar y copiar CNAME

1. Click en **[Save]**
2. Vercel te mostrará:

```
┌─────────────────────────────────────────────────────────┐
│ Configure DNS for www.vidarelax.com.co                  │
│                                                          │
│ Type   Name   Value                                     │
│ ────────────────────────────────────────────────────── │
│ CNAME  www    cname.vercel-dns.com  [Copy]             │
└─────────────────────────────────────────────────────────┘
```

3. Click en **[Copy]** y **ANOTAR:** `cname.vercel-dns.com`

---

## PASO 4: Resumen de valores copiados

Al final deberías tener anotados:

```
✅ PARA DOMINIO RAÍZ (vidarelax.com.co):
   Tipo: A
   Nombre: @
   Valor: _________________ ← Tu IP de Vercel

✅ PARA WWW (www.vidarelax.com.co):
   Tipo: CNAME
   Nombre: www
   Valor: cname.vercel-dns.com
```

---

## PASO 5: Estado en Vercel (antes de configurar DNS)

En la lista de dominios ahora verás:

```
┌─────────────────────────────────────────────────────────┐
│                                                          │
│ ⏳ vidarelax.com.co                    🎯 Production    │
│    Invalid Configuration                                │
│    Add DNS records shown above                          │
│                                                          │
│ ⏳ www.vidarelax.com.co                🔀 Redirect to   │
│    Invalid Configuration                vidarelax.com.co│
│    Add DNS records shown above                          │
│                                                          │
└─────────────────────────────────────────────────────────┘
```

**Esto es NORMAL.** Dice "Invalid" porque aún NO has configurado los DNS en m.icom.co.

---

## SIGUIENTE PASO: Configurar DNS en m.icom.co

Ahora que tienes los valores de Vercel, ve a m.icom.co y:

### En Registros A:
```
Subdominio: @
Dominio: vidarelax.com.co
IP: [pegar la IP que copiaste de Vercel]
```

### En Registros CNAME:
```
Subdominio: www
Dominio: vidarelax.com.co
Destino: cname.vercel-dns.com
```

(Ver GUIA-MICOM-VERCEL.md para pasos detallados en m.icom.co)

---

## VERIFICACIÓN FINAL (después de 1-4 horas)

Cuando los DNS se propaguen, en Vercel verás:

```
┌─────────────────────────────────────────────────────────┐
│                                                          │
│ ✓ vidarelax.com.co                     🎯 Production    │
│   Valid Configuration                                   │
│                                                          │
│ ✓ www.vidarelax.com.co                 🔀 Redirect to   │
│   Valid Configuration                   vidarelax.com.co│
│                                                          │
└─────────────────────────────────────────────────────────┘
```

**¡Listo!** 🎉 Tu dominio está conectado.

---

## CHECKLIST RÁPIDO

**En Vercel:**
- [ ] Add Domain: `vidarelax.com.co` → Production
- [ ] Copiar IP del registro A
- [ ] Add Domain: `www.vidarelax.com.co` → Redirect to vidarelax.com.co
- [ ] Copiar valor CNAME (cname.vercel-dns.com)

**En m.icom.co:**
- [ ] Crear registro A: @ → [IP de Vercel]
- [ ] Crear registro CNAME: www → cname.vercel-dns.com

**Verificar:**
- [ ] Esperar 1-4 horas
- [ ] Ver ✓ "Valid Configuration" en Vercel
- [ ] Probar https://vidarelax.com.co

---

**Fecha:** 2025-11-04
**Versión:** Específica para interfaz Vercel 2025
