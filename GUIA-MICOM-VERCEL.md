# GUÍA PASO A PASO - Conectar vidarelax.com.co a Vercel
## Adaptada específicamente para la interfaz de m.icom.co

---

## FASE 1: OBTENER VALORES DE VERCEL (Hacer primero)

### Paso 1.1: Acceder a Vercel
1. Ir a: https://vercel.com
2. Iniciar sesión
3. Seleccionar el proyecto: **Fundacion-VIDARELAX**

### Paso 1.2: Agregar el dominio en Vercel
1. Click en **Settings** (en el menú del proyecto)
2. Click en **Domains** (en el menú lateral)
3. Click en el botón **Add Domain**
4. Escribir: `vidarelax.com.co`
5. Click en **Add**

### Paso 1.3: Copiar los valores DNS de Vercel
Vercel te mostrará algo como esto:

```
Para configurar vidarelax.com.co:

Tipo A:
Name: @
Value: 76.76.21.21  ← COPIAR ESTE VALOR

Tipo CNAME:
Name: www
Value: cname.vercel-dns.com  ← COPIAR ESTE VALOR
```

**IMPORTANTE:** Los valores pueden variar. Usa los que Vercel te muestre.

### Paso 1.4: Repetir para www (opcional pero recomendado)
1. Click nuevamente en **Add Domain**
2. Escribir: `www.vidarelax.com.co`
3. Click en **Add**
4. Vercel te preguntará si quieres redirigir www → vidarelax.com.co
5. Seleccionar **Redirect www to vidarelax.com.co** (recomendado)

---

## FASE 2: CONFIGURAR DNS EN M.ICOM.CO

### Paso 2.1: Acceder al panel de m.icom.co
1. Ya debes estar en el panel de vidarelax.com.co
2. Buscar la sección: **Configuración DNS**
3. Click para expandir esa sección

### Paso 2.2: Verificar Name Servers (opcional)
1. Click en la pestaña: **Servidores DNS**
2. Verificar que estén configurados:
   ```
   Servidor DNS 1: clanserver01.ns.com.co
   Servidor DNS 2: clanserver02.ns.com.co
   Servidor DNS 3: clanserver03.ns.com.co
   Servidor DNS 4: clanserver04.ns.com.co (opcional)
   ```
3. Si están así, está correcto. NO CAMBIAR.

### Paso 2.3: Configurar Registro A (dominio raíz)
1. Click en la pestaña: **Registros A**
2. Verás esta interfaz:

```
┌──────────────┬────────────────┬──────────┬─────────┐
│ SUBDOMINIO   │ DOMINIO        │ IP DESTINO│ CREAR  │
├──────────────┼────────────────┼──────────┼─────────┤
│              │vidarelax.com.co│ [____]   │[Crear] │
└──────────────┴────────────────┴──────────┴─────────┘
```

3. Completar así:
   - **SUBDOMINIO:** Dejar vacío o escribir `@`
   - **DOMINIO:** vidarelax.com.co (ya viene)
   - **IP DESTINO:** Pegar la IP que Vercel te dio (ej: 76.76.21.21)

4. Click en **[Crear]**

**RESULTADO ESPERADO:**
Debe aparecer un registro creado que diga:
```
@ → vidarelax.com.co → 76.76.21.21
```

### Paso 2.4: Configurar Registro CNAME (www)
1. Click en la pestaña: **Registros CNAME**
2. Verás esta interfaz:

```
┌──────────────┬────────────────┬──────────┬─────────┐
│ SUBDOMINIO   │ DOMINIO        │ DESTINO  │ CREAR  │
├──────────────┼────────────────┼──────────┼─────────┤
│              │vidarelax.com.co│ [____]   │[Crear] │
└──────────────┴────────────────┴──────────┴─────────┘
```

3. Completar así:
   - **SUBDOMINIO:** `www`
   - **DOMINIO:** vidarelax.com.co (ya viene)
   - **DESTINO:** `cname.vercel-dns.com` (el que Vercel te dio)

4. Click en **[Crear]**

**RESULTADO ESPERADO:**
Debe aparecer un registro creado que diga:
```
www → vidarelax.com.co → cname.vercel-dns.com
```

### Paso 2.5: Verificar registros creados
Al final deberías tener:

**En Registros A:**
- 1 registro: `@ → 76.76.21.21` (o la IP que Vercel te dio)

**En Registros CNAME:**
- 1 registro: `www → cname.vercel-dns.com`

---

## FASE 3: ESPERAR Y VERIFICAR

### Paso 3.1: Tiempo de propagación
- **Mínimo:** 5-15 minutos
- **Normal:** 1-4 horas
- **Máximo:** 48 horas (raro)

### Paso 3.2: Verificar propagación DNS
1. Ir a: https://dnschecker.org
2. En el campo de búsqueda escribir: `vidarelax.com.co`
3. Seleccionar tipo: **A**
4. Click en **Search**
5. Debería mostrar la IP de Vercel en varios lugares del mundo

Repetir para www:
1. Escribir: `www.vidarelax.com.co`
2. Seleccionar tipo: **CNAME**
3. Debería mostrar: `cname.vercel-dns.com`

### Paso 3.3: Verificar en Vercel
1. Volver a Vercel → Settings → Domains
2. Al lado de vidarelax.com.co debería aparecer:
   - ⏳ **Pending** (esperando propagación) → Esperar más
   - ✅ **Valid** (configurado correctamente) → ¡Listo!
   - ❌ **Invalid** (error en configuración) → Revisar pasos

### Paso 3.4: Probar en navegador
1. Abrir navegador (Chrome, Firefox, etc.)
2. Escribir: `https://vidarelax.com.co`
3. Debería cargar el sitio de la fundación
4. Verificar el candado 🔒 (SSL activo)

También probar:
- `http://vidarelax.com.co` (debe redirigir a https)
- `https://www.vidarelax.com.co` (debe redirigir a vidarelax.com.co sin www)

---

## CHECKLIST COMPLETO

### En Vercel:
- [ ] Agregar dominio: vidarelax.com.co
- [ ] Agregar dominio: www.vidarelax.com.co
- [ ] Configurar redirect: www → sin www
- [ ] Copiar IP del registro A
- [ ] Copiar valor del CNAME

### En m.icom.co - Registros A:
- [ ] Crear registro A:
  - Subdominio: @ (o vacío)
  - Dominio: vidarelax.com.co
  - IP: [la que Vercel te dio]

### En m.icom.co - Registros CNAME:
- [ ] Crear registro CNAME:
  - Subdominio: www
  - Dominio: vidarelax.com.co
  - Destino: cname.vercel-dns.com

### Verificación:
- [ ] Esperar 1-4 horas
- [ ] Verificar en dnschecker.org (tipo A para dominio raíz)
- [ ] Verificar en dnschecker.org (tipo CNAME para www)
- [ ] Ver estado "Valid" en Vercel
- [ ] Probar https://vidarelax.com.co en navegador
- [ ] Verificar SSL activo (candado 🔒)
- [ ] Probar www (debe redirigir)

---

## PROBLEMAS COMUNES

### ❌ "No puedo crear el registro A sin subdominio"
**Solución:** En el campo SUBDOMINIO escribe `@` (arroba)

### ❌ "Ya existe un registro A"
**Solución:**
1. Busca el registro A existente
2. Edítalo o bórralo
3. Crea el nuevo con la IP de Vercel

### ❌ "El CNAME no acepta el valor"
**Solución:**
- Asegúrate de escribir exactamente: `cname.vercel-dns.com`
- NO agregues http:// ni https://
- NO agregues punto al final

### ❌ "Después de 24 horas sigue sin funcionar"
**Solución:**
1. Verificar los Name Servers (deben ser clanserver01-04.ns.com.co)
2. Revisar que los registros estén exactamente como se indicó
3. Contactar soporte de m.icom.co: atulado@...

### ❌ "Vercel dice Invalid Configuration"
**Solución:**
1. Ir a dnschecker.org y verificar que los DNS estén propagados
2. Si aparecen correctos, esperar 1 hora más
3. Si persiste, revisar que la IP sea exactamente la que Vercel indicó

---

## VALORES DE REFERENCIA

**⚠️ IMPORTANTE:** Estos son valores DE EJEMPLO. Usa los que Vercel te muestre.

```
Registro A:
-----------
Subdominio: @
Dominio: vidarelax.com.co
IP: 76.76.21.21  ← (EJEMPLO - usa el tuyo)

Registro CNAME:
---------------
Subdominio: www
Dominio: vidarelax.com.co
Destino: cname.vercel-dns.com  ← (EJEMPLO - usa el tuyo)
```

---

## SIGUIENTE PASO DESPUÉS DE CONECTAR

Una vez el dominio funcione correctamente:

1. ✅ Actualizar enlaces en redes sociales
2. ✅ Decidir sobre correos corporativos (ver mensaje-cliente-configuracion-correos.txt)
3. ✅ Configurar Web3Forms para formularios
4. ✅ Solicitar indexación en Google Search Console

---

**Fecha:** 2025-11-04
**Versión:** 1.0 - Adaptada para interfaz m.icom.co específica
