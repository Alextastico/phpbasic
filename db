---------------------------------------------------------
conexion
------------------------------------------------------------
<?php 
	$host = "localhost";
	$userDB = "root";
	$passDB = "";
	$db = "instituto";

	$conexion = mysqli_connect($host, $userDB, $passDB, $db);
?>

-----------------------------------------------------
Sesion admin
---------------------------------------------------
<?php 
	session_start();
	if (!isset($_SESSION['usuario'])) {
		echo "Sin usuario";
	}else{
		echo "usuario";
	}
	
 ?>
 ---------------------------------------------------
 Procesar Login
 --------------------------------------------------
 include("conexion.php");

			session_start();
		$usuario = $_POST["nombreUsuario"];
		$password = $_POST["passUsuario"];
		//Seleccion desde base de datos.
		$solicitud = "SELECT * FROM tabladocente";
		$resultado = mysqli_query($conexion, $solicitud);
		$row = mysqli_fetch_array($resultado);
		if ($usuario == $row['nombreDocente'] && $password == $row['runDocente']) {
			echo "Correcto";
			echo "Bienvenido" . $_SESSION['usuario'] = $usuario;
		 	header('location: admin.php');
		}else{
			echo "incorrecto";
		}
    
   ---------------------------------------------
   SELECCION y MOSTRAR
   ----------------------------------------------
   $solicitud = "SELECT * FROM datos";
$resultado = mysqli_query($conexion, $solicitud);

echo "<table border='1' <tr><td>NOMBRE y APELLIDO</td><td>EDAD</td><td>CELULAR</td><td>ACCIONES</td>";
while ($fila = mysqli_fetch_array($resultado) ){
	echo "<tr>";
	echo "<td>". $fila['Nombre']. " ". $fila['Apellido']." </td>";
	echo "<td>". $fila['Edad']. " </td>";
	echo "<td>". $fila['Celular']. " </td>";
	echo "<td><a href='tres.php?id=".$fila['ID']."'>ELIMINAR</a></td>";
	echo "</tr>";
}

echo "</table>";
------------------------------------------
INTRODUCIR A DB
____________________________________
<?php 
include("conexion.php");

$nombre = $_POST['nombre'];
$apellido = $_POST['apellido'];
$edad = $_POST['edad'];
$celular = $_POST['celular'];

$solicitud = "
	INSERT INTO datos (Nombre, Apellido, Edad, Celular) VALUES ('$nombre', '$apellido', '$edad', '$celular')";

$resultado = mysqli_query($conexion, $solicitud);	
header("location: index.php");
?>
------------------------------------------
LISTAR
----------------------------------
<?php 
include("conexion.php");

$solicitud = "SELECT * FROM datos";
$resultado = mysqli_query($conexion, $solicitud);

echo "<table border='1' <tr><td>NOMBRE y APELLIDO</td><td>EDAD</td><td>CELULAR</td><td>ACCIONES</td>";
while ($fila = mysqli_fetch_array($resultado) ){
	echo "<tr>";
	echo "<td>". $fila['Nombre']. " ". $fila['Apellido']." </td>";
	echo "<td>". $fila['Edad']. " </td>";
	echo "<td>". $fila['Celular']. " </td>";
	echo "<td><a href='tres.php?id=".$fila['ID']."'>ELIMINAR</a></td>";
	echo "</tr>";
}

echo "</table>";

 ?>
