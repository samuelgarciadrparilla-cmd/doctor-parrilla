# Dr. Parrilla — App de Gestión
## Versión 1.0 — Lista para producción

---

## PASO 1 — Crear base de datos Firebase (GRATIS, 10 min)

1. Ir a: https://console.firebase.google.com
2. Click "Agregar proyecto" → nombre: "doctor-parrilla"
3. Deshabilitar Google Analytics → Crear proyecto
4. En el menú izquierdo: "Realtime Database" → "Crear base de datos"
5. Elegir ubicación: "us-central1" → Siguiente
6. Seleccionar "Iniciar en modo de prueba" → Habilitar
7. Copiar la URL que aparece (formato: https://doctor-parrilla-xxxxx.firebaseio.com)

## PASO 2 — Pegar la URL en el código

Abrir: src/App.jsx
Buscar la línea: const FIREBASE_URL = "";
Reemplazar con: const FIREBASE_URL = "https://TU-URL-AQUI.firebaseio.com";

## PASO 3 — Publicar en Vercel (GRATIS)

### Opción A — Sin GitHub (más fácil desde PC)
1. Instalar Node.js desde: https://nodejs.org (versión LTS)
2. Abrir terminal en esta carpeta
3. npm install
4. npm install -g vercel
5. vercel login  (abre el navegador, iniciar sesión con Gmail)
6. vercel --prod
7. Copiar el link que aparece ✓

### Opción B — Con GitHub (recomendado)
1. Crear cuenta en: https://github.com
2. Nuevo repositorio "doctor-parrilla" (privado)
3. Subir estos archivos
4. Ir a: https://vercel.com → Import from GitHub
5. Seleccionar el repositorio → Deploy
6. ¡Listo en 2 minutos!

## PASO 4 — Conectar dominio (ej: doctorparrilla.com)
1. Comprar en: https://namecheap.com (~$12/año)
2. En Vercel → Settings → Domains → Add domain
3. Copiar los nameservers que indica Vercel → pegarlos en Namecheap
4. Esperar 5-15 min → ¡Activo!

---

## Usuarios Administradores
| Nombre          | Teléfono     | Rol               |
|-----------------|--------------|-------------------|
| Samuel García   | 0991935364   | CEO               |
| Jorge           | 0981707549   | Gerente General   |
| David           | 0992369143   | Jefe de Producción|
| Dalila García   | 0982234753   | Presidente        |

## Sincronización Firebase
- Cuando Firebase está configurado: todos los admins ven los mismos datos en tiempo real
- El indicador "🔥 Firebase sync" aparece cuando está conectado
- Sin Firebase: datos guardados localmente por dispositivo

## Reglas de Firebase (para producción)
Ir a Firebase → Realtime Database → Reglas → Pegar esto:
{
  "rules": {
    "drparrilla": {
      ".read": true,
      ".write": true
    }
  }
}
