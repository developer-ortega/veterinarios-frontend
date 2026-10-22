# APV Frontend — Administrador de Pacientes de Veterinaria

Aplicación web (SPA) para que un veterinario administre sus pacientes: se registra, confirma su cuenta por email, inicia sesión y gestiona su listado de pacientes desde un panel privado.

**Demo en línea (Netlify):** `https://apv-mern-developer-ortega.netlify.app`

> El backend está en el plan gratuito de Render: la primera acción (por ejemplo, iniciar sesión) puede tardar entre 30 y 60 segundos si el servicio estaba inactivo.

Proyecto realizado como parte de un curso FullStack con JavaScript (Udemy), desplegado por mi cuenta como parte de mi portafolio. La API está en [veterinarios-backend](https://github.com/developer-ortega/veterinarios-backend).

## Funcionalidades

- Registro de usuarios y confirmación de cuenta por enlace de email
- Inicio de sesión con JWT y rutas protegidas (`/admin`)
- Recuperación de contraseña por email
- Panel para crear, editar y eliminar pacientes
- Edición de perfil y cambio de contraseña
- Mensajes de validación y de error del servidor en pantalla
- Diseño responsivo

## Stack técnico

- **React 19** + **JavaScript**
- **Vite** como bundler y servidor de desarrollo
- **React Router** para el enrutamiento (rutas públicas y protegidas)
- **Context API** + hooks personalizados (`useAuth`, `usePacientes`) para el estado global
- **Axios** para consumir la API
- **Tailwind CSS 4** para los estilos
- **Netlify** para el despliegue

## Estructura del proyecto

```
src/
├── components/   # Componentes reutilizables (Header, Formulario, Paciente, Alerta, etc.)
├── config/       # Instancia de Axios con la URL del backend
├── context/      # AuthProvider y PacientesProvider
├── hooks/        # useAuth y usePacientes
├── layout/       # AuthLayout y RutaProtegida
├── pages/        # Login, Registrar, Confirmar cuenta, Panel de pacientes, Perfil...
└── App.jsx       # Definición de rutas
```

## Cómo correrlo localmente

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/developer-ortega/veterinarios-frontend.git
   cd veterinarios-frontend
   ```

2. Instalar dependencias:
   ```bash
   npm install
   ```

3. Crear un archivo `.env` en la raíz (usar `.env.example` como referencia) con la URL de tu backend:
   ```
   VITE_BACKEND_URL=http://localhost:4000
   ```
   Para que todo funcione, el [backend](https://github.com/developer-ortega/veterinarios-backend) debe estar corriendo.

4. Iniciar el servidor de desarrollo:
   ```bash
   npm run dev
   ```

## Scripts disponibles

```bash
npm run dev       # Servidor de desarrollo
npm run build     # Genera el build de producción en /dist
npm run preview   # Sirve el build localmente
npm run lint      # Ejecuta ESLint
```

## Despliegue

El sitio se publica en Netlify desde este repositorio. La variable `VITE_BACKEND_URL` apunta a la API en Render, y el archivo `public/_redirects` permite que las rutas de React Router funcionen al recargar la página.
