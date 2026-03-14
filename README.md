# actividad ud05.1 - regex, xml y xsd

## qué he hecho
En esta actividad he creado un archivo XML con datos de usuarios y un archivo XSD para validar que esos datos estén bien escritos.

## archivos del repositorio
- `usuarios.xml`
- `usuarios.xsd`
- `README.md`

## estructura del xml
El XML tiene un elemento raiz llamado `usuarios` y dentro hay varios elementos `usuario`.

Cada usuario tiene:
- nombreCompleto
- email
- telefono
- codigoPostal
- nombreUsuario
- contrasena

Tambien he añadido un atributo `id` en cada usuario.

## restricciones que he usado

### email
He usado una expresion regular para comprobar que tenga una estructura normal de correo:
- texto antes de la arroba
- una arroba `@`
- dominio
- extension

Patron:
`[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}`

### telefono
He puesto que tenga 9 cifras y que empiece por 6, 7, 8 o 9, porque he seguido el formato español.

Patron:
`[6789][0-9]{8}`

### codigo postal
He puesto 5 cifras y que los dos primeros numeros vayan del 01 al 52, que son los codigos de provincia en España.

Patron:
`(0[1-9]|[1-4][0-9]|5[0-2])[0-9]{3}`

### nombre de usuario
He puesto que:
- empiece por una letra minuscula
- solo pueda tener minusculas, numeros, punto y guion bajo
- tenga entre 4 y 20 caracteres

Patron:
`[a-z][a-z0-9._]{3,19}`

### contrasena
He puesto que tenga:
- minimo 8 caracteres
- una mayuscula
- una minuscula
- un numero
- un simbolo

En XSD lo he hecho con varios patrones a la vez.

## validacion
He relacionado el XML con el XSD usando esta linea:

`xsi:noNamespaceSchemaLocation="usuarios.xsd"`

Despues se puede comprobar en VS Code con una extension de XML/XSD que el archivo es valido.

