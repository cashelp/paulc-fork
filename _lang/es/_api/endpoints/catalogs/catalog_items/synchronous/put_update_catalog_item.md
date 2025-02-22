---
nav_title: "COLOCAR: Actualizar Artículo del Catálogo"
article_title: "COLOCAR: Actualizar Artículo del Catálogo"
search_tag: Endpoint
page_order: 6

layout: api_page
page_type: reference
description: "En este artículo se describen los detalles del punto final Actualizar elemento del catálogo de Braze."

---
{% api %}
# Actualizar elemento del catálogo
{% apimethod put %}
/catalogs/{catalog_name}/items/{item_id}
{% endapimethod %}

> Utiliza este punto final para actualizar un elemento de tu catálogo. 

Si no se encuentra `item_id`, este punto final creará el elemento en tu catálogo. Este punto final es síncrono.

{% apiref postman %}https://documenter.getpostman.com/view/4689407/SVYrsdsG?version=latest#b2871ed7-734e-4a37-b8f1-e11584e569f5 {% endapiref %}

## Requisitos previos

Para utilizar este punto final, necesitarás una [clave de API]({{site.baseurl}}/api/basics#rest-api-key/) con el permiso `catalogs.replace_item`.

## Límite de velocidad

{% multi_lang_include rate_limits.md endpoint='synchronous catalog item' %}

## Parámetros de la ruta

| Parámetro | Obligatoria | Tipo de datos | Descripción |
|---|---|---|---|
| `catalog_name` | Obligatoria | Cadena | Nombre del catálogo. |
| `item_id` | Obligatoria | Cadena | El ID del elemento del catálogo. |
{: .reset-td-br-1 .reset-td-br-2 .reset-td-br-3 .reset-td-br-4}

## Parámetros de la solicitud

| Parámetro | Obligatoria | Tipo de datos | Descripción |
|---|---|---|---|
| `items` | Obligatoria | Matriz | Una matriz que contiene objetos elemento. Los objetos de artículo deben contener campos que existan en el catálogo, excepto el campo `id`. Sólo se permite un objeto artículo por solicitud. |
{: .reset-td-br-1 .reset-td-br-2 .reset-td-br-3 .reset-td-br-4}

## Ejemplo de solicitud

```
curl --location --request PUT 'https://rest.iad-03.braze.com/catalogs/restaurants/items/restaurant1' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer YOUR-REST-API-KEY' \
--data-raw '{
  "items": [
    {
      "Name": "Restaurant",
      "Loyalty_Program": false,
      "Location": {
        "Latitude": 33.6112,
        "Longitude": -117.8711
      },
      "Top_Dishes": [
        "Hamburger",
        "Deluxe Cheeseburger"
      ],
      "Open_Time": "2021-09-03T09:03:19.967+00:00"
    }
  ]
}'
```

## Respuesta

Existen tres respuestas de código de estado para este punto final: `200`, `400` y `404`.

### Ejemplo de respuesta satisfactoria

El código de estado `200` podría devolver el siguiente cuerpo de respuesta.

```json
{
  "message": "success"
}
```

### Ejemplo de respuesta de error

El código de estado `400` podría devolver el siguiente cuerpo de respuesta. Consulta la sección [Solución de problemas](#troubleshooting) para obtener más información sobre los errores que puedas encontrar.

```json
{
  "errors": [
    {
      "id": "invalid-fields",
      "message": "Some of the fields given do not exist in the catalog",
      "parameters": [
        "id"
      ],
      "parameter_values": [
        "restaurant1"
      ]
    }
  ],
  "message": "Invalid Request"
}
```

## Solución de problemas

La siguiente tabla enumera los posibles errores devueltos y sus pasos asociados para la solución de problemas.

| Error | Solución de problemas |
| --- | --- |
| `arbitrary-error` | Se ha producido un error arbitrario. Inténtalo de nuevo o ponte en contacto con [el servicio de asistencia]({{site.baseurl}}/support_contact/). |
| `catalog-not-found` | Comprueba que el nombre del catálogo es válido. |
| `filtered-set-field-too-long` | El valor del campo se está utilizando en un conjunto filtrado que supera el límite de caracteres de un elemento. |
| `id-in-body` | Elimina cualquier ID de elemento en el cuerpo de la solicitud. |
| `ids-too-large` | El límite de caracteres para cada ID de artículo es de 250 caracteres. |
| `invalid-ids` | Los caracteres admitidos para los nombres de ID de artículo son letras, números, guiones y guiones bajos. |
| `invalid-fields` | Confirma que todos los campos que estás enviando en la solicitud API ya existen en el catálogo. Esto no está relacionado con el campo ID mencionado en el error. |
| `invalid-keys-in-value-object` | Las claves de los objetos del artículo no pueden incluir `.` ni `$`. |
| `item-already-exists` | El artículo ya existe en el catálogo. |
| `item-array-invalid` | `items` debe ser una matriz de objetos. | 
| `items-too-large` | El límite de caracteres para cada elemento es de 5000 caracteres. |
| `request-includes-too-many-items` | Sólo puedes crear un elemento de catálogo por solicitud. |
| `too-deep-nesting-in-value-object` | Los objetos elemento no pueden tener más de 50 niveles de anidamiento. |
| `unable-to-coerce-value` | Los tipos de elementos no se pueden convertir. |
{: .reset-td-br-1 .reset-td-br-2}

{% endapi %}