# Servidor-Cliente - Angel Luna Lugo
## 🌐 Trabajo del lado del servidor y del cliente  /  MoonDev

En el desarrollo web, es común trabajar tanto del lado del servidor como del lado del cliente para construir aplicaciones completas. Next.js permite manejar ambos aspectos en una sola plataforma, facilitando el desarrollo de aplicaciones web modernas.

### Del lado del cliente (Frontend)

El trabajo del lado del cliente se refiere a todo lo que el usuario ve e interactúa directamente en su navegador. Es la interfaz de usuario que responde a las interacciones, ejecutando JavaScript para actualizar el contenido de la página sin necesidad de recargarla por completo.

### Del lado del servidor (Backend)

El trabajo del lado del servidor se enfoca en manejar la lógica de negocio, la interacción con bases de datos y la entrega de contenido al cliente. Next.js permite realizar renderizado del lado del servidor (SSR), lo que significa que se puede generar HTML en el servidor antes de enviarlo al cliente.

### Ejemplo básico en Next.js

Next.js es un framework de React que permite construir aplicaciones completas con renderizado del lado del cliente y del servidor en una sola aplicación.

#### **Código de ejemplo**

```javascript
'use client'; // Asegura que este componente se ejecute en el lado del cliente

// pages/index.js
export async function getServerSideProps() {
  // Lógica del lado del servidor
  const res = await fetch('http://localhost:3000/api/saludo');
  const data = await res.json();

  return {
    props: { mensaje: data.mensaje },
  };
}

export default function Home({ mensaje }) {
  return (
    <div>
      <h1>{mensaje}</h1>
      <button onClick={() => alert('Este es un mensaje del lado del cliente.')}>
        Haz clic aquí
      </button>
    </div>
  );
}

