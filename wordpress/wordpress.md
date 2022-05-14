


Cuando ponemos el wordpress en otra URL, debemos modificar algunos registros en la DB para que funcione bien.


UPDATE wp_options SET option_value = replace(option_value, 'http://www.dominioactual.com', 'http://www.dominionuevo.com') WHERE option_name = 'home' OR option_name = 'siteurl';

UPDATE wp_posts SET guid = replace(guid, 'http://www.dominioactual.com', 'http://www.dominionuevo.com');

UPDATE wp_posts SET post_content = replace(post_content, 'http://www.dominioactual.com', 'http://www.dominionuevo.com');

UPDATE wp_postmeta SET meta_value = replace(meta_value, 'http://www.dominioactual.com', 'http://www.dominionuevo.com');

----------------------------------------------------------------------------------------------------------------------------------------------

17-junio-2020
INSTALACION DE WP DESDE CERO

_ https://es-ar.wordpress.org/download/
_ Crear DB / user en el server
_ Cambiar nombre wp-config-sample.php
  Y configurarlo
_ ir al dominio http://midominio.com/
 Vamos a configurar user admin / y clave


-----------------------------------------
Desactivar plugins de WP por db por si migramos y hay algo que no funciona..

tabla wp_options -> active_plugins eliminar ese texto


