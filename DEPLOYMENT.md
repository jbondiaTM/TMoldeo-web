# Guía de Despliegue - TMoldeo Web

## Opciones de Despliegue

### 1. Vercel (Recomendado)

Vercel es ideal para aplicaciones React y ofrece despliegue automático desde Git.

#### Pasos:
1. Crear cuenta en [vercel.com](https://vercel.com)
2. Conectar repositorio de GitHub
3. Configurar proyecto:
   - Framework: Vite
   - Build Command: `pnpm run build`
   - Output Directory: `dist`
4. Desplegar automáticamente

#### Configuración adicional:
```json
// vercel.json
{
  "rewrites": [
    { "source": "/(.*)", "destination": "/index.html" }
  ]
}
```

### 2. Netlify

Otra excelente opción para sitios estáticos.

#### Pasos:
1. Crear cuenta en [netlify.com](https://netlify.com)
2. Conectar repositorio
3. Configurar build:
   - Build command: `pnpm run build`
   - Publish directory: `dist`
4. Configurar redirects para SPA

#### Configuración:
```
# _redirects file in public/
/*    /index.html   200
```

### 3. GitHub Pages

Para despliegue gratuito desde GitHub.

#### Configuración:
```yaml
# .github/workflows/deploy.yml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    
    - name: Setup Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '18'
        
    - name: Install pnpm
      run: npm install -g pnpm
      
    - name: Install dependencies
      run: pnpm install
      
    - name: Build
      run: pnpm run build
      
    - name: Deploy
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./dist
```

### 4. Servidor Propio (VPS/Dedicado)

Para mayor control y personalización.

#### Requisitos:
- Servidor con Node.js
- Nginx o Apache
- Certificado SSL

#### Configuración Nginx:
```nginx
server {
    listen 80;
    server_name tmoldeo.com www.tmoldeo.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name tmoldeo.com www.tmoldeo.com;
    
    ssl_certificate /path/to/certificate.crt;
    ssl_certificate_key /path/to/private.key;
    
    root /var/www/tmoldeo/dist;
    index index.html;
    
    location / {
        try_files $uri $uri/ /index.html;
    }
    
    # Cache static assets
    location ~* \.(js|css|png|jpg|jpeg|gif|ico|svg)$ {
        expires 1y;
        add_header Cache-Control "public, immutable";
    }
}
```

## Configuración de Dominio

### DNS Records
```
Type    Name    Value
A       @       [IP_DEL_SERVIDOR]
CNAME   www     tmoldeo.com
```

### SSL Certificate
- Usar Let's Encrypt para certificados gratuitos
- Configurar renovación automática

## Variables de Entorno

Para diferentes entornos, crear archivos:

```bash
# .env.development
VITE_API_URL=http://localhost:3000
VITE_ANALYTICS_ID=

# .env.production
VITE_API_URL=https://api.tmoldeo.com
VITE_ANALYTICS_ID=GA_TRACKING_ID
```

## Optimizaciones Post-Despliegue

### 1. CDN
- Configurar CloudFlare o AWS CloudFront
- Mejorar tiempos de carga globales

### 2. Monitoring
- Google Analytics
- Google Search Console
- Uptime monitoring

### 3. SEO
- Sitemap.xml
- Robots.txt
- Meta tags específicos por página

### 4. Performance
- Comprimir imágenes
- Lazy loading
- Service Workers para cache

## Checklist Pre-Despliegue

- [ ] Build exitoso sin errores
- [ ] Todas las rutas funcionan correctamente
- [ ] Formularios validados y funcionales
- [ ] Imágenes optimizadas
- [ ] Meta tags configurados
- [ ] Certificado SSL configurado
- [ ] Analytics implementado
- [ ] Backup del código fuente

## Mantenimiento Post-Despliegue

### Actualizaciones Regulares
1. Revisar dependencias mensualmente
2. Actualizar contenido según necesidades
3. Monitorear performance y errores
4. Backup regular de la base de datos (si aplica)

### Monitoreo
- Configurar alertas de downtime
- Revisar métricas de performance
- Analizar comportamiento de usuarios

## Soporte y Troubleshooting

### Problemas Comunes

**Error 404 en rutas:**
- Verificar configuración de redirects
- Asegurar que el servidor maneja SPA correctamente

**Imágenes no cargan:**
- Verificar rutas absolutas vs relativas
- Comprobar permisos de archivos

**Formulario no funciona:**
- Verificar configuración de backend
- Revisar CORS si hay API externa

### Logs y Debugging
- Usar herramientas de desarrollo del navegador
- Configurar logging en servidor
- Monitorear errores con Sentry o similar

---

**Nota**: Esta guía asume conocimientos básicos de desarrollo web y administración de servidores. Para asistencia técnica específica, contactar al equipo de desarrollo.

