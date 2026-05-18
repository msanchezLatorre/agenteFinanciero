# Asesor Financiero — Guía de Deploy

## Requisitos previos
- Cuenta en GitHub (gratis): https://github.com
- Cuenta en Vercel (gratis): https://vercel.com
- API Key de Anthropic: https://console.anthropic.com

---

## Pasos para publicar en la web

### 1. Subir el proyecto a GitHub

1. Abrí https://github.com/new
2. Creá un repositorio nuevo llamado `asesor-financiero` (privado recomendado)
3. En tu computadora, abrí una terminal en la carpeta del proyecto y ejecutá:

```bash
git init
git add .
git commit -m "primer commit"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/asesor-financiero.git
git push -u origin main
```

### 2. Conectar Vercel con GitHub

1. Entrá a https://vercel.com y creá una cuenta (podés usar tu cuenta de GitHub)
2. Hacé click en **"Add New Project"**
3. Seleccioná tu repositorio `asesor-financiero`
4. Vercel detecta automáticamente que es Next.js — no cambies nada
5. Hacé click en **"Deploy"**

### 3. Agregar tu API Key de Anthropic

**Esto es el paso más importante — sin esto el agente no funciona.**

1. En Vercel, entrá a tu proyecto
2. Andá a **Settings → Environment Variables**
3. Agregá:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** tu API key (empieza con `sk-ant-...`)
   - **Environment:** Production, Preview, Development (tildá los 3)
4. Hacé click en **Save**
5. Volvé a **Deployments** y hacé **Redeploy** para que tome la variable

### 4. Listo 🎀

Vercel te da una URL del tipo:
```
https://asesor-financiero-xxx.vercel.app
```

Esa es tu app en la web, accesible desde cualquier dispositivo.

---

## Cómo obtener tu API Key de Anthropic

1. Entrá a https://console.anthropic.com
2. Andá a **API Keys** → **Create Key**
3. Copiá la key (solo se muestra una vez)
4. Pegala en Vercel como se indica arriba

**El costo aproximado:** cada consulta al asesor cuesta ~$0.01-0.03 USD dependiendo de la longitud.

---

## Actualizaciones futuras

Cada vez que hagas cambios al código:
```bash
git add .
git commit -m "descripcion del cambio"
git push
```
Vercel re-deploya automáticamente en ~30 segundos.
