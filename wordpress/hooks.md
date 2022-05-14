
# HOOKS
-----------------------------------------------------------------------




## Que son los hooks

Acciones y filtros
https://codex.wordpress.org/Plugin_API

acá tenemos documentación del orden de las acciones sería en una request, dentro del FRONT
https://codex.wordpress.org/Plugin_API/Action_Reference
Debajo de esto está el titulo
"Actions Run During an Admin Page Request"
es decir el orden de las hooks pero dentro del ADMIN

Por otro lado están los hooks filtros; que modifican un dato que se muestre en el momento, no deberían modificar otra cosa,
acá la referencia -> https://codex.wordpress.org/Plugin_API/Filter_Reference





## Action Hooks

son uno de los dos tipos de hooks

crear una funcion callback y otra add_action() 'nombre de la accion' / 'nombre de la funcion q llama'
se le puede pasar la prioridad y cantidad de args aceptados...

`add_action (
            string $tag,
        callable $function,
        int $priority = 10,
        int $accepted_args = 2   
    )
`

antes de esto debe haber un
do_action('save_post', $parms1, $parms2);

Luego entonces vamos a poner el add_action
add_action( 'save_post', 'name_funct_save,post', 10, 2);
entonces acá llamamos a la función, con prioridad de 10 y pasando 2 argumentos que son los que van en do_action()







## Filters Hooks
-------------


se modifica data de otras acciones.
estos filtros están preparados para trabajar de manera aislada no afectando nada de manera global.
add_filter()



## Custom Hooks
--------

do_action( $tag, $args); -> hook de acción
apply_filters( $tag, $value, $args); -> hook de filtro




## Removiendo Acciones y Filtros
-------

remove_action() -> eliminamos función callback del hook
remove_all_actions() -> eliminamos todas las funciones callbak del hook


## Determinando el gancho actual y la cantidad de ejecución
-----------
Tenemos funciones que nos dice desde que hook nos llamaron, de esta manera una misma func()
puede ser llamada desde ganchos diferentes.
Current_action()
Current_filter()
