[1] introducción--------------------------------------------------------------

[2] Preparándose para empezar-------------------------------------------------

[3] Conceptos básicos del plugin----------------------------------------------


Para poder ver documentación:
https://developer.wordpress.org/


3 componentes princ wp

nucleo
temas
plugins


plugin:
app añade funcionalidad adicional o nueva caracteristica al software. es un complemento.



[3-10]
primeras funciones importantes al crear wp

register_activation_hook() -> se ejecuta una vez que activamos el plugin desde admin
register_desactivation_hook() -> se ejecuta una vez que desactivamos el plugin desde el admin
register_uninstall_hook() -> cuando desisntalamos

acciones y filtros
acciones: añadir o cambiar funcionalidad
filtros: modificar contenido a medida que se carga en el wp

Se escribe todo a partir de API
las más utilizadas:
PluginAPI / optionsAPI / SettingsAPI / HttpAPI / ShortcodeAPI

Documentación:
https://make.wordpress.org/core/handbook/best-practices/

DIR
wp-content/plugins/myownplugin -> acá debemos crear el plugin





[3-11]
Comentarios de cabecera al inicio del plugina. Al menos debe tener el nombre. Copiar de un ejemplo de un plugin.


[3-12] Incluyendo una licencia
Licencias al inicio del plugin


[3-13] Ganchos de activación y desactivación (hooks)
Detalla las funciones nombradas en [3-10]
Explica que podemos crear tablas personalizadas por ejemplo en la activación...



[3-14] Métodos de desinstalación
Como se mencionó tenemos el hook de uninstall,
y también puede haber un archivo "uninstall.php" -> Se ejecuta cuando desde admin desinstalamos plugin


[3-15] Mejores Practicas
Define estructura de dirs ordenados
Utilizar MVC
Hay un repo en donde está bien estructurado para copiar eso:
https://github.com/DevinVinson/WordPress-Plugin-Boilerplate
Usar is_admin() para detectar si el user es admin. importante!


[4] Seguridad en nuestro plugin------------------------------------------------


[4-16] Comprobación de las capacidades de usuario
Roles de usuario
Capacidades de cada usuario. SuperAdmin, Adminstrador, editor, etc
función importante -> current_user_can( $captabalitie )

docs -> https://wordpress.org/support/article/roles-and-capabilities/




[4-17] Validación de datos---------------

Si recibimos datos del usuario debemos validar los datos

de php: isset() empty() mb_strlen() strlen() preg_match() strpos() count() in_array()

de WP: is_email() term_exists() username_exists() validate_file() *_exists() *_validate() is_*()
docs -> https://developer.wordpress.org/reference/ -> todas las funciones de WORDPRESS incluidas








[4-18] Asegurando la entrada de datos
funcionces de WP para esto -> sanitiza_*()
docs -> https://developer.wordpress.org/themes/theme-security/data-sanitization-escaping/




[4-19] Asegurando la salida de datos

Seguridad para ataques asegurando salida -> esc_*()
docs -> idem anterior, están las dos juntas
ver por ejemplo para internalización, esc_html__()

[4-20] Nonces
Nos ayudan a verificar la solicitud al server es x seguridad

wp_create_nonce() -> nos crea token user y ventana de tiempo
wp_verify_nonce() -> controlamos el token








[5] Creación de menús en la administración----------------------------------



[5-21] Menús de nivel superior-----------------------------

para agregar un menú al panel ADMIN a través de action 'admin_menu' -> https://developer.wordpress.org/reference/hooks/admin_menu/

add_menu_page(7 atributos) -> https://developer.wordpress.org/reference/functions/add_menu_page/





[5-22] Submenús---------------------------------------------

add_submenu_page(); -> https://developer.wordpress.org/reference/functions/add_submenu_page/ 





[13] Usuarios---------------------------------------------------------------------------------------



[13-58] Breve introducción-------------------------------------------------------------------------



[13-59] Creando Usuarios, forma básica-------------------------------------------------------------
desde panel admin
wp_create_user()
username_exists() / email_exists() / wp_generate_password

[13-60] Forma Compleja-------------------------------------------------------------------------
wp_insert_user (mixto $userdata)
https://developer.wordpress.org/reference/functions/wp_insert_user/



[13-61] Obteniendo info de un usuario-------------------------------------------------------------------------
get_userdata( id )



[13-62] Obteniendo info del usuario actual-------------------------------------------------------------------------
wp_get_current_user();



[13-63] Actualizando los usuarios-------------------------------------------------------------------------
wp_update_user( complejo $userdata)

[13-64] Eliminando los usuarios-------------------------------------------------------------------------
wp_delete_user( id )

[13-65] Metada de Usuarios - Agregando campo-------------------------------------------------------------------------
add_user_meta() / get_user_meta() / update_user_meta() / delete_user_meta()
Hooks
user_new_form() -> pagina de agregar usuario
user_register() -> Para guardar desde la pagina de agregar usuario
.....


[13-66] Cambios en los archivos-------------------------------------------------------------------------
acá tenemos el código fuente de este capitulo



[13-67] Manipulando los roles-------------------------------------------------------------------------
add_role() / remove_role() / get_role()
wp_roles()
https://developer.wordpress.org/plugins/users/roles-and-capabilities/



[13-68] Manipulando el rol de un usuario-------------------------------------------------------------------------


[13-69] Manipulando las capacidades de un rol-------------------------------------------------------------------------


[13-70] Manipulando las capacidades de un usuario-------------------------------------------------------------------------



[13-71] Métodos y funciones faltantes-------------------------------------------------------------------------




[10-26]-------------------------------------------------------------------------







[10-27]-------------------------------------------------------------------------











