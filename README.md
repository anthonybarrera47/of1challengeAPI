# Proyecto de Pruebas con Postman y Newman

Este proyecto contiene una colección de pruebas automatizadas para verificar la API de `thecatapi.com`. Utilizamos Postman para definir y ejecutar las pruebas y Newman para la ejecución en línea de comandos y CI/CD.

## Requisitos

- [Node.js](https://nodejs.org/) (versión 20)
- [Postman](https://www.postman.com/downloads/) (opcional, pero útil para el desarrollo y pruebas manuales)
- [Newman](https://www.npmjs.com/package/newman)

## Instalación

1. Clonar este repositorio:

    ```sh
    git clone https://github.com/anthonybarrera47/of1challengeAPI.git
    cd of1challengeAPI
    ```

2. Instalar Newman globalmente:

    ```sh
    npm install -g newman
    ```

## Configuración

1. Configurar el entorno de Postman:

    - Abre Postman y navega a la sección de **Environments**.
    - Crea un nuevo entorno llamado `DeUna Environment`.
    - Añade las siguientes variables al entorno:
        - `YOUR-API-KEY`: Tu clave de API para `thecatapi.com`.
        - `endpoint`: `https://api.thecatapi.com/`

    También puedes utilizar el archivo de entorno proporcionado (`environment.json`).

2. Exporta la colección de Postman y el entorno:

    - Exporta la colección de Postman como un archivo JSON (`TheDogAPIcollection.json`).
    - Exporta el entorno de Postman como un archivo JSON (`environment.json`).

3. Asegúrate de que la URL de la solicitud en la colección use la variable de entorno `endpoint`, por ejemplo:

    ```plaintext
    {{endpoint}}v1/images/search
    ```

## Ejecución de Pruebas

Para ejecutar las pruebas con Newman, usa el siguiente comando:

```sh
newman run path/to/your_collection.json -e path/to/your_environment.json
