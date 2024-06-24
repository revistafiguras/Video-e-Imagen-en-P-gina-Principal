## Código para colocar el video en la página Principal de OJS 3

Vamos a la ruta en el servidor: /var/www/html/ojs/templates/frontend/pages y entramos al archivo indexJournal.tpl

Una vez dentro del archivo indexJournal.tpl buscamos esta parte del código al principio:


<div class="page_index_journal">

        {call_hook name="Templates::Index::journal"}        
        {* Additional Homepage Content *}
        {if $additionalHomeContent}
                <div class="additional_content">
                        {$additionalHomeContent}
                </div>
        {/if}...
        

Se agrega la linea de la etiqueta 
<video style="width: 100%; height: 100%;" autoplay="" muted="" loop="" playsinline><source src="https://revistafiguras.acatlan.unam.mx/public/journals/1/Video_Vol5_num2.mp4" type="video/mp4" alt=""></video>

La agregamos junto con sus parámetros style, autoplay, muted y loop, esta línea se ajustará al 100% del bloque lateral izquierdo quedando asi...




<div class="page_index_journal">

        {call_hook name="Templates::Index::journal"}
        <video style="width: 100%; height: 100%;" autoplay="" muted="" loop="" playsinline><source src="https://revistafiguras.acatlan.unam.mx/public/journals/1/Video_Vol5_num2.mp4" type="video/mp4" alt=""></video>
        {* Additional Homepage Content *}
        {if $additionalHomeContent}
                <div class="additional_content">
                        {$additionalHomeContent}
                </div>
        {/if}

El video que vaya a agregarse debe de estar en la ruta: /var/www/html/ojs/public/journals/1
Este video debe enviarse desde una computadora al servidor con el comando scp. 
