# Clase Date en javaScript

La clase Date se utiliza para obtener fechas, el formato original de dichas fechas se da en un numero que representa lo milisegundos transcurridos desde 1970, la clase Date proporciona métodos para dar formato a dichos milisegundos



#### Date()

`Date()`

retorna: 

`'Tue Feb 13 2024 06:57:41 GMT-0500 (hora estándar de Colombia)'`

Retorna en forma de  candena de texto la fecha y hora en un formato compuesto por día, mes, día en numero, hora en horas, minutos y segundos y la zona horaria.



#### new Date()

`new Date()`

Esto devuelve un objeto que contiene la fecha en el mismo formato que el  `Date()` solo que es un tipo de dato diferente, a está instancia le podemos pasar por parámetro datos de la fecha y dicho objeto le da un formato predefinido 

`new Date("December 20, 2010, 12:30")`

Salida:

`Mon Dec 20 2010 12:30:00 GMT-0500 (hora estándar de Colombia)`



## Métodos estáticos 

los métodos estáticos no requieren ser instanciados, se instancian "automáticamente"

#### Date.now()

Solo devuelve la hora en milisegundos transcurrida desde 1 de enero de 1970

`Date.now() = 1707826901971`

#### Date.parse()

si le pasamos el formato de una fecha, nos devuelve el tiempo transcurrido en milisegundos desde la fecha inicial de la clase Date hasta la fecha que le pasemos al método parse.

`let instancia = new Date()`

`instancia.setTime(Date.parse("December 10, 1971"))`

Salida:

61189200000 milisegundos,  desde 1 de enero de 1970 hasta el 10 de diciembre de 1971



## Métodos de instanciación 

para acceder a estos métodos y poder manipular las fechas obviamente debemos instanciar la clase Date().

```js
let objeto = new Date("February 26, 1998 12:02:00")
Thu Feb 26 1998 12:02:00 GMT-0500 (hora estándar de Colombia) //salida
```

#### getDate()

Con este método podemos obtener el día del mes en formato de número 

```js
let diaMes = objeto.getDate()
```

`diaMes = 26`



#### getDay()

Obtener el día de la semana, de la fecha especificada.

```js
let diaSemana = objeto.getDay()
```

 `diaSemana = 4`



#### getFullYear()

Obtiene el año, de la fecha especificada.

```js
let año = objeto.getFullYear()
```

 `año = 1998`



#### getHours()

Obtiene la hora, de la fecha especificada.

```js
let hora = objeto.getHours()
```

`hora = 12`



#### getMiliseconds()

Obtiene los milisegundos, de la fecha especificada en el constructor, en este caso no especifiqué los milisegundos, así que este método me va a devolver 0.

```js
let mls = objeto.getMilliseconds()
```

`mls = 0`



#### getMinutes()

Obtiene los minutos, de la fecha especificada

```js
let minutos = objeto.getMinutes()
```

`minutos = 02`



#### getMonth()

Obtiene el número del mes, pero recordemos que los meces comienzan a contarse desde el 0

```js
let mes = objeto.getMonth()
```

`mes = 1`



#### getSeconds()

Obtiene los segundos, de la fecha especificada 

```js
let segundos = objeto.getSeconds()
```

`segundos = 0`



#### getTime()

Obtenemos un numero que representa los milisegundos hasta la fecha que le indicamos.

```js
let tiempo = objeto.getTime()
```

`tiempo = 888512520000`



#### getTimezoneOffset()

Muestra la diferencia en minutos entre la fecha con zona horaria UTC y la zona horaria local 

```js
const date1 = new Date('August 19, 1975 23:15:30 GMT+07:00');
const date2 = new Date('August 19, 1975 23:15:30 GMT-02:00');
```

```js
console.log(date1.getTimezoneOffset()); // = 300
```

#### getUTCDate()

Obtenemos el día del mes, de acuerdo con al tiempo universal

```js
date1.getUTCDate(); // = 19
```

 

#### getUTCDay()

Devuelve el día de la semana de acuerdo al tiempo universal 

```js
let diaMes = objeto.getUTCDay()
```

`diaMes = 4`



#### getUTDFullYear()

Obtener el año de la fecha según el tiempo universal

```js
let año = objeto.getUTCFullYear()
```

`año = 1998`



#### getUTCHours()

Obtenemos la hora según la fecha del tiempo universal 

```js
let horas = objeto.getUTCHours()
```

`hora = 17`



#### getUTCMilliseconds()

Obtenemos los milisegundos según la fecha del tiempo universal

```js
let mls = objeto.getUTCMilliseconds() // = 0
```



##### Los siguientes métodos obtienen un dato especifico de acuerdo al tiempo universal

mes = getUTCMonth()

segundos = getUTCSeconds()



```js
let objeto = new Date("February 26, 1998 12:02:00")
```



### setDate()

Método usado para cambiar el día del mes de una fecha dada.

```js
objeto.setDate(16)
```

Ahora el día será 16 



#### setFullYear()

Se puede fijar un año especifico con este método.

```js
objeto.setFullYear(1997)
```



#### setHours()

Con esté método podemos modificar las horas, minutos y segundos de nuestra fecha, enviando como parámetros estos datos respectivamente.

```js
objeto.setHours(11, 59, 59)
```



### Los sets permiten modificar la fecha local 

Estos son los métodos:

Milisegundos: setMilliseconds()

Minutos: setMinutes()

Meses: setMonth()

Segundos: setSeconds()



### Tiempo universal

Los siguientes métodos permiten cambiar partes del formato de la fecha con base al tiempo universal 

Día del mes: setUTCDate()

Año: setUTCFullYear()

Horas: setUTCHours()

Milisegundos: setUTCMilliseconds()

Minutos: setUTCMinutes()

Mes: setUTCMonth()

Segundos: setUTCSeconds()



## Formatos 

#### toDateString()

Este método devuelve la fecha en un formato fácil de entender

```js
objeto.toDateString()// = 'Sun Feb 16 1997'
```



#### toISOString()

Este método devuelve la fecha en formato ISO 

```JS
objeto.toISOString() // = '1997-02-16T16:59:59.000Z'
```



#### toJSON()

Retorna la fecha en forma de string, esto es para preparar la fecha para ser usada por json, la fecha se muestra en formato toISOString()

```js
objeto.toJSON() // salida = '1997-02-16T16:59:59.000Z'
```



#### toLocaleDateString()

Permite definir el idioma y el formato en que queremos que se muestre la fecha.

```javascript
const date = new Date();
const dateString = date.toLocaleDateString();
console.log(dateString); // Output: "2/13/2024" (format may vary based on the default locale)

const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
const formattedDate = objeto.toLocaleDateString("sp-SP", options)
console.log(formattedDate); // Output: 'domingo, 16 de febrero de 1997
```



#### toLocaleString()

Permite definir el idioma en que queremos que se muestre la fecha y en la hora coloca si es am o pm

```js
objeto.toLocaleString() // Salida = '16/2/1997, 11:59:59 a. m.'
```



#### toLocaleTimeString()

Muestra la hora con am y pm y permite especificar el idioma 

```js
objeto.toLocaleTimeString() // Salida = '11:59:59 a. m.'
```



#### toString()

Devuelve un string que representa la hora local 

```
objeto.toString() // Salida = 'Sun Feb 16 1997 11:59:59 GMT-0500 (hora estándar de Colombia)'
```



#### valueOf()

Muestra el numero de milisegundos transcurridos desde 1 de enero de 1970 hasta la fecha que le indicamos.

```
objeto.valueOf() // 856112399000
```







https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Date