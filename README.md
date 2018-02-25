# ysf2ea7ee
Esto es autoria del amigo Manuel EA7EE.
Modificacion del codigo fuente del YSF2DMR del Andy (CA6JAU).

Instrucciones de ejecución:
EN PRINCIPIO ES UN BIN, Y PARA PRUEBAS SOLAMENTE FUNCIONA EN LA IMAGEN PI-STAR.

Para hacerlo funcionar ahi que darle propiedades de ejecucion:
sudo chmod a+x YSF2DMR

El archivo YSF2DMR.ini, en la imagen PI-STAR ha de estar en:
/etc/YSF2DMR.ini

Esta versión es un poco más complicada, sobre todo por el GPS. Envío un fichero de ejemplo con las secciones de APRS. 
La clave de APRS-IS la podéis obtener aqui: https://apps.magicbug.co.uk/passcode/
La APIKey de desarrollador es muy sencillo conseguirla, solo tenéis que registraros aqui: https://aprs.fi/page/api
Espero que podáis probarla, yo la probaré un poco más antes de seguir adelante. 
Tarda unos segundos en retirar la info GPS de la red, en los primeros cambios no aparece la info GPS, hay que esperar al menos un cambio para ver la información. Si no se ha encontrado la info GPS (lo podéis ver en el log) no envia info GPS y por tanto en el equipo no os aparece la distancia.

Ver 0.12:
Añadido envío de posicionamiento GPS a aprs.fi. Es necesario introducir clave de APRS-IS
Añadido recolección de datos de aprs.fi para envio a equipos C4FM. Si hay varias posibilidades recoger la primera que encuentra aunque no sea la más actualizada. Es necesario clave de desarrollador APIKey de aprs.fi. Refresca cada 240 segundos la posición, configurable en el archivo ini.
Añadido nueva sección de APRS en fichero INI. Se adjunta fichero ini de ejemplo.
Añadida nueva entrada en sección DMRNetwork para desactivar la desconexión automática para redes que no sean Braindmeister
Añadida etiqueta para TG 9, etiqueta "LOCAL"
Eliminada la posibilidad de conexión directa a TG 4000 para evitar problemas
Añadido procesamiento de tecla WIRES de desconexión (normalmente el asterisco), su pulsación implica un envío de petición 4000 y paso a TG 9 (LOCAL)
Paso de de 10 a 12 segundos en timeout de cambio TG.
Ahora todas las transacciones con el nodo no generan tráfico en la red

Ver. 0.11:
Paso de de 6 a 10 segundos en timeout de cambio TG.
Añadida Espera a fin de mensaje de desconexión
Permite conexión directa al loro a través del código 9990
Añadida etiqueta PARROT y UNLINK para enlaces 9990 y 4000
Arreglado otros fallos menores

Ver. 0.10:
Implementada respuesta a petición info repetidor WIRES (DX)
Implementado cambio automático de TG via WIRES(CONNECT).
No permite entrada en red DMR a usuarios no estén en DMRID database.
Cierra programa de forma correcta cuando se recibe SIGTERM.
