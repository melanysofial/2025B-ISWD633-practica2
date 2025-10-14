# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.

Consultar: 
Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).


Los Docker Secrets guardan y protegen la información confidencial sin tener que ponerlos directamente en el código, en lla imagen del contenedor o en variables de entorno, los secretos se crean cifrados, solo se asignan a los servicios autorizados, son temporales en lo contenedores y se borran al terminar.
Primero se crea con el comando docker secret create para guardar el dato que se desea.
