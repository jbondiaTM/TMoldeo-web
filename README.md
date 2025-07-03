# TMoldeo - Sitio Web Corporativo

## Descripción del Proyecto

Sitio web moderno y profesional para TMoldeo, empresa especializada en soluciones técnicas de inyección de plásticos. El sitio está diseñado para captar leads, mostrar servicios y establecer credibilidad en el sector industrial.

## Características Principales

### Diseño y UX
- **Diseño responsivo**: Adaptable a todos los dispositivos (desktop, tablet, móvil)
- **Estética moderna**: Colores corporativos azul y naranja, tipografía limpia
- **Navegación intuitiva**: Menú claro con todas las secciones principales
- **Elementos interactivos**: Animaciones sutiles, contadores animados, scroll to top

### Funcionalidades
- **Formulario de contacto**: Con validación y estado de loading
- **Galería de casos reales**: Testimonios y casos de éxito detallados
- **Recursos descargables**: Sección de recursos gratuitos
- **Información de servicios**: Descripción detallada de cada servicio
- **Sección de colaboradores**: Logos de empresas partner

### Tecnologías Utilizadas
- **React 19**: Framework principal
- **Vite**: Build tool y servidor de desarrollo
- **Tailwind CSS**: Framework de estilos
- **Lucide React**: Iconografía
- **React Router**: Navegación entre páginas

## Estructura del Proyecto

```
tmoldeo-web/
├── public/
│   ├── hero-machine.jpg          # Imagen principal de máquina
│   ├── mold-injection.jpg        # Imagen de molde
│   ├── plastic-products.webp     # Imagen de productos
│   ├── tmoldeo-logo.png          # Logo generado
│   └── industrial-background.png # Fondo industrial
├── src/
│   ├── components/
│   │   ├── Header.jsx            # Navegación principal
│   │   ├── Footer.jsx            # Pie de página
│   │   ├── ScrollToTop.jsx       # Botón scroll to top
│   │   ├── AnimatedCounter.jsx   # Contador animado
│   │   └── LoadingSpinner.jsx    # Spinner de carga
│   ├── pages/
│   │   ├── Home.jsx              # Página de inicio
│   │   ├── About.jsx             # Sobre nosotros
│   │   ├── Services.jsx          # Servicios
│   │   ├── Cases.jsx             # Casos reales
│   │   ├── Resources.jsx         # Recursos gratuitos
│   │   └── Contact.jsx           # Contacto
│   ├── App.jsx                   # Componente principal
│   └── App.css                   # Estilos globales
└── dist/                         # Build de producción
```

## Páginas del Sitio

### 1. Inicio (/)
- Hero section con llamada a la acción
- Sección de problemas/soluciones
- Testimonios de clientes
- CTA final

### 2. Sobre Nosotros (/sobre-nosotros)
- Historia de la empresa
- Estadísticas con contadores animados
- Valores corporativos
- Equipo de trabajo

### 3. Servicios (/servicios)
- Lista detallada de servicios
- Precios y duraciones
- Proceso de trabajo
- Beneficios

### 4. Casos Reales (/casos-reales)
- Casos de éxito por material (PA66, PP, ABS)
- Estadísticas de resultados
- Metodología de trabajo

### 5. Recursos Gratuitos (/recursos-gratuitos)
- Recursos descargables
- Filtros por categoría
- Newsletter signup

### 6. Contacto (/contacto)
- Formulario de contacto con validación
- Métodos de contacto directo
- FAQ
- Información de ubicación

## Instalación y Desarrollo

### Requisitos Previos
- Node.js 18+
- pnpm (recomendado) o npm

### Instalación
```bash
# Clonar el repositorio
git clone [url-del-repositorio]

# Navegar al directorio
cd tmoldeo-web

# Instalar dependencias
pnpm install

# Iniciar servidor de desarrollo
pnpm run dev

# Construir para producción
pnpm run build
```

### Scripts Disponibles
- `pnpm run dev`: Inicia el servidor de desarrollo
- `pnpm run build`: Construye la aplicación para producción
- `pnpm run preview`: Previsualiza el build de producción

## Optimizaciones Implementadas

### Performance
- Lazy loading de imágenes
- Componentes optimizados
- Build optimizado con Vite
- CSS minificado

### SEO
- Meta tags apropiados
- Estructura semántica HTML
- URLs amigables
- Contenido optimizado

### UX/UI
- Diseño responsivo
- Tiempos de carga rápidos
- Navegación intuitiva
- Feedback visual en formularios

## Próximas Mejoras Sugeridas

1. **Integración con CRM**: Conectar formularios con sistema de gestión
2. **Analytics**: Implementar Google Analytics
3. **Chat en vivo**: Widget de chat para consultas inmediatas
4. **Blog**: Sección de artículos técnicos
5. **Área de clientes**: Portal privado para clientes existentes
6. **Multiidioma**: Soporte para inglés y otros idiomas

## Mantenimiento

### Actualizaciones de Contenido
- Los textos se pueden modificar directamente en los archivos de componentes
- Las imágenes se almacenan en la carpeta `public/`
- Los estilos globales están en `src/App.css`

### Despliegue
El proyecto está listo para desplegarse en cualquier servicio de hosting estático como:
- Vercel
- Netlify
- GitHub Pages
- AWS S3 + CloudFront

## Contacto Técnico

Para soporte técnico o modificaciones del sitio web, contactar al equipo de desarrollo.

---

**Desarrollado con ❤️ para TMoldeo**

