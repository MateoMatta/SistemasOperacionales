*1. Cree dos archivos de texto similares (con una o dos líneas diferentes). Compárelos empleando diff.*
Con el comando ```diff  (get-content texto.txt) (get-content texto2.txt)``` se obtiene
_Resultado:_

InputObject        SideIndicator
-----------        -------------
Pruebita de taller =>           
                   =>           
La prueba          <=      

*2. Qué ocurre si se ejecuta:
*get-service | export-csv servicios.csv | out-file
Por qué?*

No puede procesar el argumento porque el "path" es nulo, por lo cual no guarda en un archivo .csv los Servicios del computador mismo.

*3. Cómo haría para crear un archivo delimitado por puntos y comas (;)? PISTA: Se emplea export-csv, pero con un parámetro adicional.*
Con el comando: ```get-service | Export-csv servicios.csv -Delimiter  ';'``` 

*4. Export-cliXML y Export-CSV modifican el sistema, porque pueden crear y sobreescribir archivos. Existe algún parámetro que evite la sobreescritura de un archivo existente? Existe algún parámetro que permita que el comando pregunte antes de sobresscribir un archivo?*
El parámetro ```-NoClobber``` evita la sobreescritura, mientras que ```-Confirm``` arroja el diálogo de pregunta acerca de sobrescribir o no.

5. Windows emplea configuraciones regionales, lo que incluye el separador de listas. En Windows en inglés, el separador de listas es la coma (,). Cómo se le dice a Export-CSV que emplee el separador del sistema en lugar de la coma?*
  
  
  NO SE
*6. Identifique un cmdlet que permita generar un número aleatorio.*

_Respuesta:_ con el cmdlet  ```get-random```

*7. Identifique un cmdlet que despliegue la fecha y hora actuales.*

_Respuesta:_ con el cmdlet  ```get-date```

*8. Qué tipo de objeto produce el cmdlet de la pregunta 7?*

un objeto tipo: "Datetime", casteado a ojeto String.

*9. Usando el cmdlet de la pregunta 7 y select-object, despliegue solamente el día de la semana, así:
   DayOfWeek
   ---------
    Thursday
    *
   Con el comando ```(get-date).DayOfWeek``` se despleiga solo el día del objeto "get-date".
    
*10. Identifique un cmdlet que muestre información acerca de parches (hotfixes) instalados en el sistema.*

_Respuesta:_ con el cmdlet  ```get-hotfix```

*11. Empleando el cmdlet de la pregunta 10, muestre una lista de parches instalados. Luego extienda la expresión para ordenar la lista por fecha de instalación, y muestre en pantalla únicamente la fecha de instalación, el usuario que instaló el parche, y el ID del parche. Recuerde examinar los nombres de las propiedades.*

_Respuesta:_

*12. Complemente la solución a la pregunta 11, para que el sistema ordene los resultados por la descripción del parche, e incluya en el listado la descripción, el ID del parche, y la fecha de instalación. Escriba los resultados a un archivo HTML.*

*13. Muestre una lista de las 50 entradas más nuevas del log de eventos System. Ordene la lista de modo que las entradas más antiguas aparezcan primero; las entradas producidas al mismo tiempo deben ordenarse por número índice. Muestre el número índice, la hora y la fuente para cada entrada. Escriba esta información en un archivo de texto plano.*


