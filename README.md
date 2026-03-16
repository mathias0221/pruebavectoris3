# Vectoris Global - Plataforma de Envíos

Plataforma web completa para una agencia de envíos que ofrece servicios de casilleros en USA y China para enviar paquetes a Venezuela.

## 🚀 Características

### Página Pública
- ✅ Hero section con llamadas a la acción
- ✅ Calculadora de envíos inteligente con fórmulas exactas
- ✅ Sección de beneficios
- ✅ Página de tarifas actualizables
- ✅ Recursos educativos públicos
- ✅ Sistema de registro con 15 preguntas de seguridad
- ✅ Página de login profesional

### Sistema de Recuperación de Acceso
- ✅ Flujo "Olvidé mi Contraseña" (3 pasos)
- ✅ Flujo "Olvidé mi Usuario" (3 pasos)
- ✅ Flujo "Olvidé Ambos" (3 pasos)
- ✅ Validación con preguntas de seguridad

### Área de Clientes
- ✅ Dashboard personal con estadísticas
- ✅ Gestión de paquetes e instrucciones
- ✅ Modal para dar instrucciones de envío
- ✅ Centro de recursos educativos exclusivos
- ✅ Sistema de guardado de recursos
- ✅ Gestión de perfil y seguridad

### Dashboard Administrativo
- ✅ Panel de control con estadísticas en tiempo real
- ✅ Gestión de solicitudes de casilleros
- ✅ Sistema de asignación con doble verificación
- ✅ Gestión de instrucciones de clientes
- ✅ Carga masiva de paquetes desde Excel
- ✅ Gestión de recursos educativos
- ✅ Configuración de tarifas dinámica
- ✅ Listas personalizadas de clientes
- ✅ Reportes y estadísticas avanzadas

### Sistema de Notificaciones
- ✅ 10 tipos de correos automáticos configurables
- ✅ Plantillas HTML responsivas
- ✅ Notificaciones de estado de envíos
- ✅ Correos de recuperación de acceso

## 🛠️ Tecnología

- **Frontend**: Next.js 14 (App Router) con TypeScript
- **Estilos**: Tailwind CSS + shadcn/ui
- **Base de Datos**: PostgreSQL con Prisma ORM
- **Autenticación**: NextAuth.js con JWT
- **Componentes**: Lucide React (íconos)
- **Formularios**: React Hook Form + Zod
- **Notificaciones**: React Hot Toast
- **Correos**: Resend / Nodemailer
- **Gráficos**: Recharts
- **Excel**: SheetJS / XLSX
- **PDF**: react-pdf / pdf.js

## 📋 Requisitos

- Node.js 18+ 
- PostgreSQL 14+
- npm o yarn

## 🚀 Instalación

1. **Clonar el repositorio**
```bash
git clone <repository-url>
cd vectoris-global
```

2. **Instalar dependencias**
```bash
npm install
```

3. **Configurar variables de entorno**
```bash
cp .env.local.example .env.local
```

Editar `.env.local` con tus credenciales:
```env
DATABASE_URL="postgresql://username:password@localhost:5432/vectoris_global"
NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-secret-key-here"
RESEND_API_KEY="your-resend-api-key"
EMAIL_FROM="noreply@vectorisglobal.com"
```

4. **Configurar base de datos**
```bash
# Generar cliente Prisma
npx prisma generate

# Crear tablas
npx prisma db push

# (Opcional) Ejecutar seed
npm run db:seed
```

5. **Iniciar servidor de desarrollo**
```bash
npm run dev
```

La aplicación estará disponible en `http://localhost:3000`

## 📁️ Estructura del Proyecto

```
src/
├── app/                    # Páginas Next.js 14 (App Router)
│   ├── (auth)/            # Rutas de autenticación
│   ├── (dashboard)/        # Rutas protegidas de clientes
│   ├── (admin)/           # Rutas administrativas
│   ├── registro/           # Página de registro
│   ├── login/              # Página de login
│   ├── tarifas/            # Página de tarifas
│   ├── recursos/           # Recursos públicos
│   └── page.tsx           # Página principal
├── components/
│   ├── layout/             # Header, Footer
│   ├── home/               # Componentes de página principal
│   ├── ui/                 # Componentes UI reutilizables
│   └── forms/              # Formularios específicos
├── lib/
│   ├── prisma.ts           # Cliente de base de datos
│   ├── utils.ts            # Utilidades generales
│   └── auth.ts             # Configuración de autenticación
├── types/
│   └── index.ts           # Definiciones de tipos TypeScript
└── prisma/
    └── schema.prisma        # Esquema de base de datos
```

## 🎨 Identidad Visual

### Colores
- **Azul Profundo**: #0A2F44 (Header, footer, botones primarios)
- **Azul Oscuro**: #1A4B6D (Hover de botones)
- **Gris Profesional**: #F5F7FA (Fondos de secciones)
- **Blanco Puro**: #FFFFFF (Fondos, textos sobre azul)
- **Gris Texto**: #4A5568 (Textos secundarios)
- **Acento Naranja**: #F97316 (Botones de acción)
- **Acento Verde**: #10B981 (Éxito, confirmación)
- **Acento Rojo**: #EF4444 (Errores, cancelar)
- **Acento Púrpura**: #8B5CF6 (Recursos educativos)

### Tipografía
- **Títulos**: Montserrat / Poppins
- **Cuerpo**: Inter / Open Sans

## 📊 Funcionalidades Destacadas

### Calculadora de Envíos
- ✅ Fórmulas exactas para peso dimensional (L×A×A÷166)
- ✅ Cálculo de volumen y pies cúbicos
- ✅ Tarifas dinámicas configurables
- ✅ Recomendación inteligente de modo de envío
- ✅ Comparación de costos en tiempo real

### Sistema de Seguridad
- ✅ Contraseñas hasheadas con bcrypt
- ✅ Preguntas de seguridad hasheadas
- ✅ JWT para autenticación
- ✅ Rate limiting en login y recuperación
- ✅ Protección contra XSS y CSRF

### Gestión Administrativa
- ✅ Control total de tarifas
- ✅ Asignación de casilleros con doble verificación
- ✅ Carga masiva desde Excel
- ✅ Reportes exportables
- ✅ Listas personalizadas de clientes

## 🚀 Despliegue

### Vercel (Recomendado)
```bash
# Instalar Vercel CLI
npm i -g vercel

# Desplegar
vercel --prod
```

### Docker
```bash
# Construir imagen
docker build -t vectoris-global .

# Ejecutar contenedor
docker run -p 3000:3000 vectoris-global
```

## 📝 Scripts Disponibles

- `npm run dev` - Servidor de desarrollo
- `npm run build` - Construir para producción
- `npm run start` - Servidor de producción
- `npm run lint` - Ejecutar linter
- `npm run db:push` - Sincronizar base de datos
- `npm run db:studio` - Abrir Prisma Studio
- `npm run db:seed` - Poblar base de datos

## 🔧 Configuración

### Base de Datos
El esquema completo está definido en `prisma/schema.prisma` con:
- Clientes y casilleros
- Paquetes e instrucciones
- Envíos y seguimiento
- Recursos educativos
- Tarifas configurables
- Sistema de notificaciones

### Correos Automáticos
Configurar en `.env.local` las variables:
- `RESEND_API_KEY` - API key de Resend
- `EMAIL_FROM` - Correo remitente

Los correos incluyen:
- Bienvenida y activación de casillero
- Notificación de nuevos paquetes
- Confirmación de instrucciones
- Actualización de estado de envíos
- Recuperación de acceso

## 🤝 Contribuir

1. Fork del proyecto
2. Crear rama feature (`git checkout -b feature/amazing-feature`)
3. Commit cambios (`git commit -m 'Add amazing feature'`)
4. Push a la rama (`git push origin feature/amazing-feature`)
5. Abrir Pull Request

## 📄 Licencia

Este proyecto está bajo licencia MIT.

## 🆘️ Soporte

Para soporte técnico:
- 📧 Correo: soporte@vectorisglobal.com
- 💬 WhatsApp: +58 414-1234567
- 🌐 Web: https://vectorisglobal.com

---

**Vectoris Global** - Tu aliado de confianza para envíos internacionales 🌍✈️🚢
