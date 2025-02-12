# Desafío 4: Agente de Compra/Venta de Coches

## Objetivo
Crear un agente que automatice el proceso de compra y venta de coches en un concesionario para los clientes. El agente debe ser capaz de:
- Valorar un coche a partir de una imagen o una descripción en texto proporcionada por el cliente, determinando su precio de mercado.
- Consultar una base de datos en Airtable para obtener el precio de un modelo específico en caso de que el cliente esté interesado en comprar un coche.
- Recopilar datos de contacto y detalles de la operación, tales como nombre, apellido, teléfono, correo electrónico, tipo de operación (compra o venta) y el nombre del modelo del coche.
- Enviar toda la información recopilada a un Google Sheets mediante una Custom Tool.

## Funcionalidades

### Evaluación del Valor del Coche

El agente deberá analizar el input del cliente, que puede ser una imagen o una descripción en texto, para estimar el valor del coche según el mercado. Esto puede lograrse mediante:
- Una Chain Tool que procese el input y devuelva una estimación del precio del coche.
- Otro Chatflow que pueda conectarse mediante una Chatflow Tool que tenga la capacidad de valorar coches.
- Herramientas de búsqueda o personalizadas.

### Consulta a Base de Datos en Airtable

Si el cliente está interesado en comprar un coche del concesionario, el agente deberá tener la capacidad de consultar en una base de datos en Airtable los modelos de coches disponibles, sus precios y sus usos principales.

Base de datos con los coches: [https://airtable.com/appr8aU4iQfB8lobf/shrBCl5n7htiRCIDy]

### Recopilación de Datos del Cliente
Independientemente de si se realiza una operación de compra o de venta, el agente deberá solicitar y recopilar la siguiente información:
- Nombre
- Apellido
- Teléfono
- Correo electrónico
- Tipo de operación (Compra o Venta)
- Modelo del coche (a comprar o vender)

### Envío de Datos a Google Sheets
Una vez recopilada y validada la información de compra/venta, se utilizará una Custom Tool para enviar los datos a un Google Sheets a través de un webhook. Esta herramienta se programará en JavaScript y utilizará variables para transmitir correctamente la información.

## Requisitos Técnicos
- **Integración con Airtable:** El agente debe ser capaz de usar los datos contenidos dentro del Airtable y extraer el precio de los coches que tenemos a la venta en caso de intención de compra.
- **Valoración de Mercado:** Implementar herramientas que permitan valorar el coche del cliente, ya sea si sube una foto de se coche o la información por escrito.
- **Uso de Herramientas Avanzadas:** Emplear una Custom Tool para la integración con Google Sheets, y utilizar una Chain Tool u otras herramientas según se requiera para la evaluación y consulta de datos.

## Ejemplo de Código para la Custom Tool (Envío a Google Sheets)

```javascript
const fetch = require('node-fetch');
const url = 'https://tu-webhook-url.com'; // Reemplazar con la URL del webhook

const body = {
  "nombre": $vars.nombre,
  "apellidos": $vars.apellidos,
  "correo": $vars.correo,
  "telefono": $vars.telefono,
  "tipoOperacion": $vars.tipoOperacion,
  "modeloCoche": $vars.modeloCoche,
  "valorCoche": $vars.valorCoche
};

const options = {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(body)
};

try {
  const response = await fetch(url, options);
  const text = await response.text();
  return text;
} catch (error) {
  console.error(error);
  return 'Error al enviar datos';
}

```