╔═══════════════════════════════════════════════════════════════════════╗
║   GUÍA: Quitar Protección de Rama Main en GitHub                     ║
╚═══════════════════════════════════════════════════════════════════════╝

PASO 1: Ir a Configuración del Repositorio
═══════════════════════════════════════════════════════════════════════

1. Ir a: https://github.com/nicolas2456/Fundacion-VIDARELAX

2. Click en la pestaña "Settings" (⚙️ Configuración)
   → Está arriba, a la derecha, junto a "Insights"

3. Si no ves "Settings", asegúrate de:
   - Estar logueado en tu cuenta (nicolas2456)
   - Tener permisos de administrador en el repositorio


PASO 2: Ir a Branch Protection Rules
═══════════════════════════════════════════════════════════════════════

1. En el menú lateral izquierdo, buscar sección "Code and automation"

2. Click en: "Branches" (Ramas)
   → Está en el menú lateral izquierdo

3. Verás una sección: "Branch protection rules"


PASO 3: Verificar si Hay Protección Activa
═══════════════════════════════════════════════════════════════════════

Busca si hay alguna regla para la rama "main":

OPCIÓN A - Si ves una regla para "main":
   ┌────────────────────────────────────────┐
   │ Branch name pattern: main              │
   │ [Edit] [Delete]                        │
   └────────────────────────────────────────┘

   → Continúa al PASO 4

OPCIÓN B - Si NO ves ninguna regla:
   ┌────────────────────────────────────────┐
   │ No branch protection rules defined     │
   │ [Add rule]                             │
   └────────────────────────────────────────┘

   → ¡NO HAY PROTECCIÓN! El problema es otro.
   → Pasa al PASO 5 (Verificar otras restricciones)


PASO 4: Eliminar la Regla de Protección
═══════════════════════════════════════════════════════════════════════

Si encontraste una regla para "main":

1. Click en "Delete" (Eliminar) al lado de la regla

2. Te pedirá confirmación:
   "Are you sure you want to delete this branch protection rule?"

3. Click en: "I understand, delete this branch protection rule"

4. ✅ Listo! La protección está eliminada


PASO 5: Verificar Otras Restricciones (si no había protección)
═══════════════════════════════════════════════════════════════════════

Si no había reglas de protección, verifica:

A) PUSH ACCESS (Acceso de Push):
   1. En "Settings" → "Branches"
   2. Buscar "Default branch" (Rama predeterminada)
   3. Verificar que "main" sea la rama predeterminada

B) REPOSITORY ACCESS (Acceso al Repositorio):
   1. En "Settings" → "Collaborators and teams"
   2. Verificar permisos de acceso
   3. Si hay restricciones, puede estar bloqueando los pushes


PASO 6: Verificar que Funcionó
═══════════════════════════════════════════════════════════════════════

Después de quitar la protección, avísame y yo intentaré el push:

git push origin main

Si funciona, verás:
   ✅ To https://github.com/nicolas2456/Fundacion-VIDARELAX.git
      xxxxx..xxxxx  main -> main


╔═══════════════════════════════════════════════════════════════════════╗
║                      CAPTURA DE PANTALLA ESPERADA                     ║
╚═══════════════════════════════════════════════════════════════════════╝

En Settings → Branches deberías ver algo como:

┌──────────────────────────────────────────────────────────────────────┐
│ Default branch                                                       │
│ ┌────────────────────────────────────────────────┐                  │
│ │ main                                      [⚙️] │                  │
│ └────────────────────────────────────────────────┘                  │
│ The default branch is considered the "base" branch...              │
│                                                                      │
│ Branch protection rules                                             │
│ Define branch protection rules to enforce certain workflows...     │
│                                                                      │
│ ⚠️ No branch protection rules defined                               │
│ [Add rule]                                                          │
└──────────────────────────────────────────────────────────────────────┘

Si ves "No branch protection rules defined" → Todo OK ✅


╔═══════════════════════════════════════════════════════════════════════╗
║                         SOLUCIÓN ALTERNATIVA                          ║
╚═══════════════════════════════════════════════════════════════════════╝

Si el problema persiste después de quitar la protección:

OPCIÓN: Darme acceso colaborador temporalmente
───────────────────────────────────────────────────────────────────────

Esto NO es posible con Claude Code, pero podrías:

1. Hacer tú el cambio manualmente (2 minutos)
   → Editar línea 2832 en GitHub
   → href="/documentos/... → href="documentos/...

2. O crear un Personal Access Token y dármelo
   → Settings → Developer settings → Personal access tokens
   → PERO esto es más complicado y menos seguro


╔═══════════════════════════════════════════════════════════════════════╗
║                            RESUMEN                                    ║
╚═══════════════════════════════════════════════════════════════════════╝

Pasos rápidos:
1. https://github.com/nicolas2456/Fundacion-VIDARELAX/settings/branches
2. Si hay regla para "main" → Delete
3. Confirmar eliminación
4. Avisarme
5. Yo intento push de nuevo

Tiempo estimado: 2 minutos

═══════════════════════════════════════════════════════════════════════

Avísame cuando hayas quitado la protección y volveré a intentar el push.
O si no encuentras ninguna protección, dime qué ves y buscaremos el
problema real.

═══════════════════════════════════════════════════════════════════════
