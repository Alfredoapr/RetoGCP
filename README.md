# 🚀 Reto Técnico – Proceso de Selección Turing-IA  

Este repositorio contiene la solución al reto técnico del proceso de selección de **Turing-IA**, cuyo propósito es evaluar competencias clave en **Cloud Computing**.  

---

## 📝 Actividades realizadas  

### 1️⃣ Crear un proyecto nuevo en GCP  
Se crea un nuevo proyecto con el nombre: **RetoGCP**.  

<img width="1844" height="813" alt="image" src="https://github.com/user-attachments/assets/d31ef31f-b929-4088-b3db-72a8837120a4" />

---

#### 🔹 Habilitar las APIs requeridas  
Las APIs necesarias para este reto son:  
- **Cloud Storage**  
- **Cloud Functions**  
- **Cloud Pub/Sub**  
- **Cloud Logging**  
- *(Opcional)* **Cloud Build**  

Pasos para habilitarlas:  
1. Ir al menú de navegación.  
2. Seleccionar **APIs y servicios** → **Biblioteca**.  
3. Buscar cada API en la barra de búsqueda y habilitarla.  

<img width="1846" height="866" alt="image" src="https://github.com/user-attachments/assets/0281a921-bf53-4717-8a33-acd367eb72b4" />

---

#### 🔹 Configuración de roles y permisos con IAM  
1. Ir al menú de navegación → **IAM y administración** → **IAM**.  
2. En el panel de permisos, seleccionar **Otorgar acceso**.  
3. Agregar la dirección de correo del nuevo usuario.  
4. Asignar roles: en este caso se crea un usuario con privilegios mínimos (rol de **Visualizador**), lo que permite visualizar la mayoría de los recursos de Google Cloud.  

<img width="1026" height="897" alt="image" src="https://github.com/user-attachments/assets/c5396827-6295-4aef-8588-f8b21a842e6a" />

---

### 2️⃣ Diseño de almacenamiento y automatización inicial  

Para crear un bucket en **Cloud Storage** hay que dirigirse al menú de navegación y seleccionar la opción **Cloud Storage** → **Buckets**.  

<img width="1836" height="925" alt="image" src="https://github.com/user-attachments/assets/c3d2fd86-4705-44d7-a9fa-2f8277608e85" />

---

#### 🔹 Crear bucket  
⚠️ **Aviso:** en mi caso, debido a problemas con la facturación (método de pago), no fue posible realizar este apartado.  

---

#### 🔹 Desarrollar una Cloud Function que se active automáticamente al subir un archivo al bucket  
La elección del lenguaje fue **Python** por la simplicidad que este ofrece y la siguiente es mi propuesta.  

```python
import functions_framework
import logging

# La Cloud Function se debe activar cuando un archivo se sube
@functions_framework.cloud_event
def gcs_trigger(cloud_event):
    try:
        # Obtener metadatos del evento
        data = cloud_event.data
        bucket = data.get("bucket")
        name = data.get("name")
        content_type = data.get("contentType", "desconocido")
        size = data.get("size", "0")

        # Log 
        logging.info(
            f"Nuevo archivo detectado en '{bucket}':\n"
            f" - Nombre: {name}\n"
            f" - Tipo: {content_type}\n"
            f" - Tamaño: {size} bytes"
        )

    except Exception as e:
        logging.error(f"Error procesando el evento: {e}", exc_info=True)
