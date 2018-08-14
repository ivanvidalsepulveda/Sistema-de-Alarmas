# Sistema-de-Alarmas-EstIvv


Sistema de Alarmas para Proyecto  Titulo Universidad del Bio Bio

Esta es una Aplicación Movil Android, la cual trabaja junto con un Dispositivo Arduino.
Este sistema fue creado para controlar el ingreso de personas especificas que lleven consigo una tarjeta de identificacion registrada previamente en el dispositivo arduino. Este dispositivo es capaz de leer dichas tarjetas mediante un sensor de proximidad. Como caso posible se piensa en un sistema de apoyo contra accidentes de niños en piscinas, para asi controlar el acceso a ellas, si el niño entra, notificará y alertará mediante sonidos y vibraciones en la App del dispositivo movil.

La App como el arduino manipulan una Base de Datos Mysql, modificando y leyendo valores de un Usuario en la Base de Datos, como por ejemplo el campo Estado a "Desactivado" o "Activado", 
Cuando el dispositivo arduino cambia el estado a "Activado", envía tambien una Notificación Push mediante Firebase a la App del Usuario con una prioridad 'High'.

La App de dicho Usuario detectará la Notificación enviada por Firebase, incluso estando el telefono en modo Dormido (Mode Doze), para 
lograr que la app tenga acceso a Internet y cosulte a la BD Mysql el Valor cambiado por el arduino, de encontrar que el valor fue 
cambiado a "Activado", la app ejecutará una serie de Alarmas como Sonido+Vibracion, hasta que desde la App esto se desactive presionando el Boton "Desactivar" manualmente, lo que hará cambiar el valor de la BD y detener las Alarmas (Sonido + Vibracion), O la otra opcion es
que el Arduino vuelva a cambiar el valor en la BD a "Desactivado", donde la app lo detectará y apagará las alarmas automáticamente...
Hasta un proximo cambio a "Activado" hecho por el Arduino...

La app tiene implementada el servicio 'Autenticación de Firebase' usando Emails; tambien contiene implementado un 'Servicio' ejecutado 
en primer plano con una 'Notificación de Importancia High', esto para que la aplicación se mantenga siempre en ejecución de primer plano hasta que el propio usuario cierre la sesión manualmente, esta será la unica forma de detener cerrar sesion.

Ivan Vidal Sepulveda, 2018.
