
# Sistema de Control de Proveedores

Sistema completo de gestión de proveedores con autenticación de usuarios y panel de administración.

## 🚀 Características

- ✅ Sistema de autenticación (Login/Registro)
- ✅ Panel de administración completo
- ✅ Gestión de usuarios (CRUD)
- ✅ Gestión de proveedores (CRUD)
- ✅ Generación de códigos QR
- ✅ Visualización de datos del proveedor mediante QR
- ✅ Modo oscuro/claro
- ✅ Diseño responsive
- ✅ Almacenamiento en localStorage (sin base de datos)

## 👥 Roles de Usuario

### Administrador
- Acceso completo al panel de administración
- Gestión de usuarios (crear, editar, eliminar)
- Gestión de proveedores (ver, eliminar)
- Búsqueda y filtrado de registros

### Usuario
- Registro de nuevos proveedores
- Generación de códigos QR
- Visualización de datos propios

## 🔐 Credenciales por Defecto

Al iniciar la aplicación por primera vez, se crea automáticamente un usuario administrador:

```
Email: admin@sistema.com
Contraseña: admin123
```

## 📋 Uso del Sistema

### Para Usuarios Normales

1. **Registro**: Crear una cuenta nueva desde `/register`
2. **Login**: Iniciar sesión desde `/login`
3. **Dashboard**: Registrar proveedores y generar códigos QR
4. **Escanear QR**: Ver información completa del proveedor

### Para Administradores

1. **Login**: Usar credenciales de administrador
2. **Panel Admin**: Acceso automático al panel de administración
3. **Gestión de Usuarios**: 
   - Crear nuevos usuarios
   - Editar información de usuarios
   - Eliminar usuarios
   - Asignar roles (admin/user)
4. **Gestión de Proveedores**:
   - Ver todos los proveedores registrados
   - Buscar por nombre, empresa o departamento
   - Ver detalles completos
   - Eliminar registros

## 🗂️ Estructura de Datos

### Usuario
```typescript
{
  id: string;
  email: string;
  password: string;
  fullName: string;
  role: 'admin' | 'user';
  createdAt: string;
}
```

### Proveedor
```typescript
{
  id: string;
  fullName: string;
  company: string;
  companions: string;
  visitReason: string;
  requestedBy: string;
  visitDate: string;
  licensePlate: string;
  department: string;
  registrationDate: string;
}
```

## 🌐 Rutas de la Aplicación

- `/` - Página principal (redirige según autenticación)
- `/login` - Inicio de sesión
- `/register` - Registro de nuevos usuarios
- `/dashboard` - Panel de usuario
- `/admin` - Panel de administración
- `/supplier/[id]` - Vista de detalles del proveedor (QR)

## 💾 Almacenamiento

El sistema utiliza `localStorage` para almacenar:
- `users` - Array de usuarios registrados
- `suppliers` - Array de proveedores registrados
- `auth_user` - Usuario autenticado actualmente

## 🔧 Tecnologías Utilizadas

- **Framework**: Next.js 14 (App Router)
- **Lenguaje**: TypeScript
- **Estilos**: Tailwind CSS v4
- **Componentes**: shadcn/ui
- **Iconos**: lucide-react
- **Formularios**: react-hook-form
- **QR**: qrcode.react
- **Notificaciones**: sonner

## 📦 Despliegue en GitHub

1. Crear repositorio en GitHub
2. Subir el código:
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/tu-usuario/tu-repo.git
git push -u origin main
```

3. Desplegar en Vercel:
   - Conectar repositorio de GitHub
   - Configurar proyecto Next.js
   - Desplegar automáticamente

## ⚠️ Notas Importantes

- Los datos se almacenan en localStorage (navegador)
- No hay persistencia en servidor
- Los datos se pierden al limpiar el navegador
- Para producción, se recomienda migrar a PostgreSQL
- El sistema está listo para GitHub y Vercel

## 🔄 Migración a PostgreSQL (Futuro)

El código ya está preparado para migrar a PostgreSQL:
- API routes ya implementadas
- Estructura de datos compatible
- Solo requiere configurar variables de entorno
- Cambiar localStorage por llamadas a API

## 📝 Licencia

Este proyecto es de código abierto y está disponible bajo la licencia MIT.
