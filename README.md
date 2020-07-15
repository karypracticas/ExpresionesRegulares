# ExpresionesRegulares
Expresiones Regulares:

https://www.debuggex.com/
https://regexr.com/

* El caracter (.)  -> Encuentra todo lo que es un caracter
* \d -> Encuentra los dígitos
* \w -> Todas las letras mayúsculas minúsculas, dígitos,  _
* \s -> White spaces
* * -> greedy - todo
* .* -> Busca todos los caracteres
* + -> uno o más 
    * Ejemplo:
    * [0-9] -> Equivale a poner \d
    * [a-z]
    * [A-Z]
    * [a-zA-Z0-9]
    * [a-zA-Z0-9_]
    * [a-zA-Z0-9_\.]
    * \d+[a-z] -> encuentra todos los dígitos pero al final debe haber una letra
￼


Ocurrencias o contadores:

Ejemplo:

\d{2,2} -> Busca dígitos donde el mínimo sean dos y máximo dos 
\d{2,5} -> Busca dígitos donde el mínimo sean dos y máximo sean cinco dígitos 
\d{2,} -> Busca dígitos donde el mínimo sean dos y máximo hasta el infinito

\d{2,2}[\.\-]?\d{2,2}[\.\-]?\d{2,2} -> Busca tres parejas de dígitos que estén separados opcionalmente por un punto o por un guion 

\t — Representa un tabulador.
\r — Representa el “retorno de carro” o “regreso al inicio” o sea el lugar en que la línea vuelve a iniciar.
\n — Representa la “nueva línea” el carácter por medio del cual una línea da inicio. Es necesario recordar que en Windows es necesaria una combinación de \r\n para comenzar una nueva línea, mientras que en Unix solamente se usa \n y en Mac_OS clásico se usa solamente \r.
\a — Representa una “campana” o “beep” que se produce al imprimir este carácter.
\e — Representa la tecla “Esc” o “Escape”
\f — Representa un salto de página
\v — Representa un tabulador vertical
\x — Se utiliza para representar caracteres ASCII o ANSI si conoce su código. De esta forma, si se busca el símbolo de derechos de autor y la fuente en la que se busca utiliza el conjunto de caracteres Latin-1 es posible encontrarlo utilizando “\xA9”.
\u — Se utiliza para representar caracteres Unicode si se conoce su código. “\u00A2” representa el símbolo de centavos. No todos los motores de Expresiones Regulares soportan Unicode. El .Net Framework lo hace, pero el EditPad Pro no, por ejemplo.
\d — Representa un dígito del 0 al 9.
\w — Representa cualquier carácter alfanumérico.
\s — Representa un espacio en blanco.
\D — Representa cualquier carácter que no sea un dígito del 0 al 9.
\W — Representa cualquier carácter no alfanumérico.
\S — Representa cualquier carácter que no sea un espacio en blanco.
\A — Representa el inicio de la cadena. No un carácter sino una posición.
\Z — Representa el final de la cadena. No un carácter sino una posición.
\b — Marca la posición de una palabra limitada por espacios en blanco, puntuación o el inicio/final de una cadena.
\B — Marca la posición entre dos caracteres alfanuméricos o dos no-alfanuméricos.

Negaciones:
\D -> Encuentra todo lo que no es un dígito
\W
\S -> Todo lo que no sea un espacio
[^0-5a-c] -> Encuentra todo lo que no sea del 0 al 5 ni de la a-c



—————————————————————————

Uso práctico de Expresiones Regulares:

LOGS:
^$ ->  El acento circunflejo denota el inicio de la línea y el de pesos el fin de la línea
Ejemplo: ^\d$ -> busca  linea donde se tenga un digito
	        ^\[LOG.*\[WARN\].*$ 
                 ^\[LOG.*\[ERROR\].*$ 

TELÉFONOS:
^\+?\d{2,3}[^\da-z]?\d{2,3}[^\da-z]?\d{2,3}[#pe]?\d*$ 
Ejemplo de los resultados que podría encontrar:
555658
56-58-11
56.78.11
56.78-98
65 09 87
65-09-87#123
552560e123
+521565811
