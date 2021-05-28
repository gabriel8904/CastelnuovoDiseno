# CastelnuovoDiseno

Hola!!!

https://www.castelnuovo.com.ar/index.html

-- Le agregué Google Analythics al sitio para poder registrar todos los ingresos que tengo al mismo. Lo hice con este script:

	<script async src="https://www.googletagmanager.com/gtag/js?id=UA-74117011-1"></script>
	<script>
		window.dataLayer = window.dataLayer || [];
		function gtag() { dataLayer.push(arguments); }
		gtag('js', new Date());

		gtag('config', 'UA-74117011-1');
	</script>
  
-- Después de mucho tiempo intentandolo, logre hacer un form que me devuelva el formulario de contacto a mi mail "ventas@castelnuovo.com.ar". 
   Para esto tuve que colocar un archivo send.php que en un comienzo no me funcionaba ya que el servidor de Donweb me generaba un conflicto. 
   En un foro de Donweb pude encontrar la solución. 
   
   <?php
    if(isset($_POST["nombre"]) && isset($_POST["email"]) && isset($_POST["comentario"]) ){
      $to = "ventas@castelnuovo.com.ar";
      $subject = "Mensaje Enviado";
      $contenido .= "Nombre: ".$_POST["nombre"]."\n";
      $contenido .= "Email: ".$_POST["email"]."\n\n";
      $contenido .= "Comentario: ".$_POST["comentario"]."\n\n";
      $header = "From: ventas@castelnuovo.com.ar\nReply-To:".$_POST["email"]."\n";
      $header .= "Mime-Version: 1.0\n";
      $header .= "Content-Type: text/plain";
    if(mail($to, $subject, $contenido ,$header)){
      echo "Mail Enviado con éxito";
    }
    }
    ?>
    
    Luego también me di cuenta que github no permite el envío de formularios, por lo que ésta función solo la podrán ver si ingresan a: www.castelnuovo.com.ar
    
--  Por último, tuve que agregar en archivo vacio en el directorio principal nombrado "code.nojekyll", ya que por algun motivo github no me permitia ver el sitio web. 
