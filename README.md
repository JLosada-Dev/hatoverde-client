# HatoverdeClient

Sistema de gestión integral para la industria ganadera lechera, desarrollado con [Angular](https://angular.dev/) versión 19.2.4.

![Logotipo](/public/icons/cow-head.png)

## Descripción General

HatoverdeClient es una aplicación web especializada para la gestión y monitoreo de la producción lechera y el manejo de bovinos. Esta plataforma permite a los productores registrar, visualizar y analizar datos de ordeñe, así como administrar información detallada de su ganado.

## Características Principales

- **Gestión Completa de Bovinos:**

  - Registro de datos completos por animal
  - Historial médico y eventos importantes
  - Filtrado avanzado por diversos criterios (raza, arete, etc.)

- **Monitoreo de Producción Lechera:**

  - Seguimiento en tiempo real de la producción
  - Estadísticas diarias y tendencias históricas
  - Análisis de calidad (grasa, proteínas, etc.)

- **Integración con ESP32:**

  - Recepción de datos desde dispositivos de ordeño automático
  - Configuración remota de equipos
  - Alertas en tiempo real de anomalías

- **Interfaz Moderna y Responsive:**
  - Diseño adaptativo para dispositivos móviles y escritorio
  - Experiencia fluida con Angular Standalone Components
  - Interfaz intuitiva estilizada con Tailwind CSS

## Servidor de Desarrollo

Para iniciar el servidor local de desarrollo:

```bash
ng serve
```

Una vez iniciado, navega a `http://localhost:4200/` en tu navegador. La aplicación se recargará automáticamente cuando modifiques cualquiera de los archivos fuente.

## Estructura del Proyecto

La aplicación está organizada siguiendo una arquitectura por dominios:

```text
src/app/domains/
  ├── bovine/           # Gestión de bovinos
  │   ├── components/
  │   └── pages/        # Vistas principales de bovinos
  ├── production/       # Producción lechera
  │   └── pages/
  │       └── production-esp32/  # Integración con dispositivos
  └── shared/           # Componentes y servicios compartidos
      ├── components/   # Modales y elementos de UI reutilizables
      ├── models/       # Interfaces y tipos para la aplicación
      └── services/     # Servicios para la comunicación con la API
```

## Generación de Código

Angular CLI incluye herramientas para generar código. Para crear un nuevo componente:

```bash
ng generate component domains/[dominio]/components/nombre-componente
```

Para un listado completo de los elementos generables:

```bash
ng generate --help
```

## Compilación del Proyecto

Para compilar el proyecto para producción:

```bash
ng build --configuration production
```

Los archivos compilados se almacenarán en el directorio `dist/`. Por defecto, la compilación para producción optimiza la aplicación para máximo rendimiento.

## Pruebas

### Pruebas Unitarias

Para ejecutar las pruebas unitarias con [Karma](https://karma-runner.github.io):

```bash
ng test
```

### Pruebas E2E

Para pruebas de extremo a extremo:

```bash
ng e2e
```

> Nota: Angular CLI no incluye un framework de pruebas e2e por defecto. Puedes integrar Cypress, Playwright u otro según tus necesidades.

## Tecnologías Utilizadas

- **Frontend:** Angular 19+, Tailwind CSS
- **Autenticación:** JWT
- **Comunicación API:** HttpClient
- **Estado:** Signals
- **Formularios:** Reactive Forms
- **Integración IoT:** ESP32

## Guía de Estilos y Diseño Visual

La interfaz de HatoverdeClient sigue un sistema de diseño coherente utilizando Tailwind CSS para crear una experiencia visual moderna y profesional.

### Paleta de Colores

| Color            | Código HEX | Uso                                     |
| ---------------- | ---------- | --------------------------------------- |
| Verde Primario   | `#0f766e`  | Botones principales, acentos, marca     |
| Verde Secundario | `#14b8a6`  | Elementos interactivos, datos positivos |
| Gris Oscuro      | `#1e293b`  | Fondos de tarjetas, barras laterales    |
| Azul Grisáceo    | `#334155`  | Contenedores, marcos, separadores       |
| Blanco           | `#ffffff`  | Texto sobre fondos oscuros              |
| Gris Claro       | `#f1f5f9`  | Fondos principales                      |
| Rojo Alerta      | `#ef4444`  | Mensajes de error, alertas críticas     |
| Amarillo Aviso   | `#eab308`  | Advertencias, notificaciones            |

### Componentes UI Principales

#### Tarjetas

Las tarjetas son contenedores principales para información, utilizando:

- Esquinas redondeadas (`rounded-xl`)
- Sombras sutiles (`shadow-lg`)
- Fondo oscuro para contraste (`bg-slate-800`)
- Texto claro (`text-white`)
- Espaciado interno consistente (`p-6`)

#### Botones

Los botones siguen un diseño consistente:

- Botones primarios: `bg-teal-500 hover:bg-teal-600 text-white font-semibold py-2 px-6 rounded shadow`
- Botones secundarios: `bg-slate-600 hover:bg-slate-700 text-white font-semibold py-2 px-4 rounded`
- Botones de alerta: `bg-red-500 hover:bg-red-600 text-white font-semibold py-2 px-4 rounded`

#### Formularios

Los campos de formulario tienen un estilo coherente:

- Etiquetas: `text-sm font-medium text-gray-700 dark:text-gray-300`
- Campos de entrada: `mt-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-teal-500 focus:ring focus:ring-teal-200 focus:ring-opacity-50`
- Mensajes de error: `mt-1 text-sm text-red-600`

### Iconografía y Elementos Visuales

- **Iconos:** Utilizamos íconos SVG inline para optimización y consistencia visual
- **Imágenes:** Placeholders consistentes para bovinos en `/public/img/bovine-placeholder.jpg`
- **Logotipo:** Diseño de vaca en diferentes variantes (`/public/icons/cow-head.png`, `cow-color.png`, `vaca.png`)

### Responsividad

El diseño se adapta a diferentes tamaños de pantalla utilizando:

- Clases responsive de Tailwind (sm, md, lg, xl, 2xl)
- Layout flexible con Flexbox y Grid
- Contenedores con anchos máximos para pantallas grandes
- Menú adaptativo que se convierte en hamburguesa en dispositivos móviles

### Animaciones

Transiciones sutiles para mejorar la experiencia del usuario:

- Hover en botones: `transition-colors`
- Cambios de estado: `transition-opacity`
- Modales: `transition-transform`

## Requisitos

- Node.js 18.x o superior
- NPM 10.x o superior
- Angular CLI 19.x

## Contribución

1. Clona el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/amazing-feature`)
3. Realiza tus cambios y haz commit (`git commit -m 'Add some amazing feature'`)
4. Sube los cambios a tu rama (`git push origin feature/amazing-feature`)
5. Abre un Pull Request

## Recursos Adicionales

- [Documentación de Angular](https://angular.dev/)
- [Referencia de Angular CLI](https://angular.dev/tools/cli)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [Documentación de componentes UI](https://tailwindui.com/)

---
## 🔗 Repositorios del Proyecto

Este proyecto es parte del sistema HatoVerde:

- **Frontend**: [hatoverde-client](https://github.com/JLosada-Dev/hatoverde-client)
- **Backend**: [hatoverde-api](https://github.com/JLosada-Dev/hatoverde-api)
- **IoT**: [hatoverde-esp32](https://github.com/JLosada-Dev/hatoverde-esp32)
---

© 2025 Hatoverde. Todos los derechos reservados.
