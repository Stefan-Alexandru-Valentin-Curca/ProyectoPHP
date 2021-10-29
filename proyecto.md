# Proyecto PHP Stefan y Gueorgui

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LoginApache</title>
    
  
</head>
<body style="background-color:rgb(0, 68, 255);">
    
    

    <h1 align="center">ProyectoLOGS</h1>
<tr>
    <form action="Proyectologh.php" method="post">
        <table width="60%" border="3px" align="center">
        <td>Caracter seleccionable:<input type="text"/></td>
    
        <td><select name="logs">
            <option value="error">error.log </option>
        <option value="error">acces.log</option>
     <option value="error">install.log</option>
     <td><input type="submit" value="Resultado"/></td>

    </table>
       
    </form>
    
</body>
</html>
  ```
## Codigo php 
``` php
<?php

$nombre_log = $_POST["logs"];

$ruta_log = "";

if ($nombre_log == "error"){
    $ruta_log= "C:/xampp2/apache/logs/error.log";
} else if ($nombre_log == "access"){
$ruta_log= "C:/xampp2/apache/logs/access.log";
}
else if ($nombre_log == "install"){
    $ruta_log= "C:/xampp2/apache/logs/install.log";
    }

$fichero = fopen($ruta_log,"r");
echo  "<textarea rows='30' cols='60'>";
while (!feof($fichero))
{
    $linea = fgets($fichero);
    echo $linea;
    
}
fclose ($fichero);
echo "</textarea>";


?>
```


