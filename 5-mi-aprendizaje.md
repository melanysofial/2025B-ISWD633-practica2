En esta práctica me interesó mucho como al añadir las variables de entorno se guardan los datos como contraseña de forma segura, al momento de realizar el primer ejercicio no se podian comunicar, por lo que cree una red personalizada para permitir la comunicación directa y estable, de esta forma funcionó y finalice el ejercicio con éxito. Se me complica un poco el mapeo de puertos pero en esta práctica lo reforcé.


## Consultar: 
## Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).


Los Docker Secrets guardan y protegen la información confidencial sin tener que ponerlos directamente en el código, en lla imagen del contenedor o en variables de entorno, los secretos se crean cifrados, solo se asignan a los servicios autorizados, son temporales en lo contenedores y se borran al terminar.
Primero se crea con el comando docker secret create para guardar el dato que se desea.
