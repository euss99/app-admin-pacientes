# Gestión de Pacientes Veterinarios

Esta es una aplicación para la gestión de pacientes (mascotas) de una veterinaria desarrollada con Vue.js utilizando la Composition API. Aquí podrás llevar un registro detallado de los pacientes, sus dueños y su historial médico, facilitando la administración eficiente de la clínica veterinaria.

En este proyecto, reforzaremos nuevamente varios conceptos importantes de Vue.js y la Composition API para mejorar nuestras habilidades en el desarrollo de aplicaciones web interactivas enfocadas en la gestión de datos. A continuación, explicaremos cómo aplicamos cada uno de los conceptos de la aplicación:

## Conceptos reforzados:

### 1. Creación de Componentes

Siguiendo las buenas prácticas, hemos utilizado la estructura de componentes de Vue.js para dividir la interfaz de usuario en componentes reutilizables y fáciles de mantener. Los componentes clave son:

- **Header**: Contiene la barra de navegación y otros elementos de cabecera.
- **Paciente**: Representa la lista de pacientes registrados, mostrando información básica de cada mascota y ofreciendo opciones de edición y eliminación.
- **Formulario**: Permite agregar o editar los datos de un paciente y su dueño.
- **Alerta**: Muestra mensajes de alerta para notificar si algún campo del formulario está incompleto o si el formulario se ha enviado con éxito.

### 2. Custom Events

Hemos utilizado custom events para facilitar la comunicación entre los componentes. Por ejemplo, cuando se agrega un nuevo paciente, emitimos un evento personalizado para que la lista de pacientes se actualice automáticamente y muestre al nuevo paciente registrado.

### 3. Directivas

Las directivas de Vue.js son fundamentales para manipular el DOM. Se han empleado directivas como `v-if`, `v-for`, `v-model` y otras para mostrar o esconder elementos según el estado de la aplicación y para iterar sobre la lista de pacientes.

### 4. State y Emits

Para mantener la coherencia de la interfaz y el estado de la aplicación, hemos utilizado el estado del componente para almacenar información relevante. Asimismo, hemos emitido eventos personalizados (emits) para notificar cambios en el estado y permitir que otros componentes respondan en consecuencia.

### 5. Computed

Los computed properties nos han ayudado a calcular y derivar datos en base a la información almacenada en el estado del componente. Se utilizaron computed properties para obtener datos estadísticos, como la cantidad total de pacientes registrados.

### 6. Métodos de los Arrays

Hemos utilizado métodos de arrays como `filter` y `map` para realizar búsquedas y transformaciones sobre la lista de pacientes. Estos métodos nos permiten manipular los datos de manera efectiva y obtener información relevante.

### 7. Local Storage

Para mantener la persistencia de datos, se ha utilizado el Local Storage del navegador. De esta manera, la información de los pacientes se mantiene incluso si el usuario cierra y vuelve a abrir la aplicación.

### 8. Watch

Hemos implementado la opción `watch` de Vue.js para monitorear cambios en el estado y realizar acciones específicas en respuesta a estos cambios. Por ejemplo, podríamos utilizar watch para guardar automáticamente los cambios en la lista de pacientes en el Local Storage.

### 9. Props

Se han utilizado props para pasar datos desde el componente principal a los componentes hijos. Por ejemplo, en el componente `Formulario`, utilizamos props para recibir los datos del paciente que se está editando, si es el caso, y mostrar dicha información para su edición.

## Instalación y Uso

Para utilizar está aplicación en tu entorno local, sigue estos pasos:

1. Clona este repositorio: `git clone https://github.com/euss99/app-admin-pacientes.git`
2. Navega a la carpeta del proyecto: `cd app-admin-pacientes`
3. Instala las dependencias: `npm install`
4. Inicia el servidor de desarrollo: `npm run dev`
5. Abre tu navegador y visita: `http://localhost:5173`

¡Listo! Ahora puedes gestionar pacientes y su historial médico en está aplicación de manera eficiente.

¡Que tengas una gran experiencia! 🐾
