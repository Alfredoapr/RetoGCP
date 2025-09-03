<img width="1031" height="908" alt="image" src="https://github.com/user-attachments/assets/0857e873-2ab5-44c7-95f6-89b6d1dd2ec6" /># RetoGCP
Este repositorio contiene la solución al reto técnico del proceso de selección de Turing-IA, cuyo propósito es evaluar competencias clave en Cloud Computing.

Tareas:

1.- Crear un proyecto nuevo en GCP, en este caso tiene el nombre de "RetoGCP"

<img width="1844" height="813" alt="image" src="https://github.com/user-attachments/assets/d31ef31f-b929-4088-b3db-72a8837120a4" />

2.- Una vez creado el proyecto, procedemos a la habilitación de las  APIs que son requeridas "Cloud Storage","Cloud Functions","Cloud Pub/Sub", "Cloud Logging" y opcionalmente "Cloud Build" para realizar esto nos dirigimos a al menu de navegación y seleccionamos **texto en     negritas** → **APIs y servicios** y despues **texto en negritas** → **Biblioteca**.
    Una vez hecho esto, en la barra de busquedaa ingresamos el nombre de cada una de las APIs para así habilitarlas. 

<img width="1846" height="866" alt="image" src="https://github.com/user-attachments/assets/0281a921-bf53-4717-8a33-acd367eb72b4" />

3.- Para la configuración de roles y permisos mediante IAM, hay que dirigirse nuevamente al menu de navegación y buscamos la opción  **texto en negritas** → **IAM y administración** y luego en **texto en negritas** → **IAM**
    Una vez hecho esto se puede visualizar el panel de permisos para nuestro proyecto, para crear un nuevo usuario seleccionamos la opición **texto en negritas** → **Otorgar acceso** una vez hecho esto se desplegara el apartado para para agregar un usuario. En nuestro caso     agregamos la dirección de correo del nuevo usuario y le asignamos los roles, nosotros queremos agregar un usuario con privilegios minimos, de tal forma que este tendrá un acceso básico y un rol como visualizador, es decirt, visualiza la mayoria de los recursos de    Google Cloud.
    <img width="1026" height="897" alt="image" src="https://github.com/user-attachments/assets/c5396827-6295-4aef-8588-f8b21a842e6a" />
