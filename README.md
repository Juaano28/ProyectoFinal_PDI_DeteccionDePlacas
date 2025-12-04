# ProyectoFinal_PDI_DeteccionDePlacas
# PlateGuard: Sistema de Detección Automática de Placas Vehiculares  
**Proyecto Final – Procesamiento Digital de Imágenes (2025-2)**  
Universidad [Tu universidad] – [Tu nombre completo]  
[Si es en dupla: Nombre del compañero]

## 1. Problema real que resolvemos
En el parqueadero de la universidad (y en cientos de parqueaderos/centros comerciales en Colombia) se generan largas filas en horas pico porque:
- El guardia debe identificar visualmente la placa del vehículo.
- En muchos casos aún se registra manualmente la entrada/salida.
- Esto genera congestión vehicular, pérdida de tiempo y errores humanos.

**Solución propuesta**: Un sistema de visión por computadora capaz de detectar automáticamente la ubicación exacta de la placa vehicular en tiempo real utilizando redes neuronales convolucionales.

## 2. Tarea de visión por computadora
**Detección de objetos (Object Detection)**  
→ Modelo: **YOLOv11** (Ultralytics)  
→ Clase única: `license_plate`

## 3. Objetivos del proyecto
**General**  
Desarrollar e implementar un sistema de detección de placas vehiculares basado en YOLO que sea rápido, preciso y desplegable en entornos reales.

**Específicos**  
- Alcanzar mAP@0.5 ≥ 0.92 en el conjunto de validación  
- Exportar el modelo a TorchScript y TensorFlow Lite con mínima pérdida de precisión  
- Implementar inferencia local y vía API (HuggingFace Spaces)  
- Desplegar una aplicación web funcional para pruebas en tiempo real

## 4. Dataset utilizado
**Principal**  
Dataset: [License Plate Recognition](https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e/dataset/4)  
- 7.053 imágenes de entrenamiento + validación  
- 1 clase: `license_plate`  
- Formato YOLOv11 (incluye augmentations: lluvia, noche, blur, etc.)  
- Enlace público: https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e

**Extra (opcional futuro)**  
Se podrán agregar ~200 imágenes propias capturadas en parqueaderos colombianos para mejorar robustez local.

## 5. Tecnologías y herramientas
| Etapa               | Tecnología / Librería                         | Versión / Modelo      |
|---------------------|-----------------------------------------------|-----------------------|
| Modelo              | Ultralytics YOLOv11                           | yolo11n / yolo11m     |
| Framework           | PyTorch                                       | 2.4+                  |
| Entrenamiento       | Kaggle Notebook (GPU P100)                    | -                     |
| Exportación         | TorchScript, ONNX, TensorFlow Lite            | -                     |
| Inferencia local    | Python + OpenCV                               | -                     |
| Despliegue          | Hugging Face Spaces + Gradio                  | -                     |
| Control de versiones| Git + GitHub                                  | -                     |

## 6. Estructura del repositorio
├── README.md                       ← Este archivo
├── data/                           ← data.yaml (configuración dataset)
├── notebooks/
│   ├── 01_Entrenamiento_YOLOv11.ipynb
│   ├── 02_Exportacion_y_Comparacion.ipynb
│   └── 03_Despliegue_HuggingFace.ipynb
├── scripts/
│   ├── inferencia_local.py         ← Recibe ruta de imagen y muestra detección
│   └── inferencia_api.py           ← Consume API de HuggingFace
├── weights/
│   ├── best.pt                     ← Modelo entrenado (PyTorch)
│   ├── best.torchscript            ← Exportado TorchScript
│   └── best_openvino_model/        ← (opcional)
├── presentation/
│   └── Exposicion_Proyecto_Final_PDI.pptx
└── requirements.txt

## 7. Enlaces importantes
- Repositorio GitHub: (este enlace)
- Dataset en Roboflow: https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e
- Hugging Face Space (demo en vivo): [se agrega al final]
- Base de datos (enlace Drive/Roboflow): [se agrega al final]

## 8. Estado actual del proyecto
| Tarea                             | Estado       |
|-----------------------------------|--------------|
| Dataset descargado y configurado  | ✅ Completado |
| Entrenamiento YOLOv11             | En curso     |
| Exportación del modelo            | Pendiente    |
| Inferencia local                  | Pendiente    |
| Inferencia vía API                | Pendiente    |
| Despliegue en HuggingFace         | Pendiente    |
| Presentación PowerPoint           | Pendiente    |

¡Listo para usar!  
Solo crea el repositorio en GitHub, pega este contenido como README.md y ya tienes una cara profesional desde el minuto 1.

Cuando me digas **“vamos con fase 1”**, te paso:
- La estructura exacta de carpetas (para que crees todo de una)
- El enlace de descarga directa del dataset en formato YOLOv11 (un clic)
- El `data.yaml` listo
- El notebook de entrenamiento que solo tendrás que ejecutar mañana en Kaggle

¿Listo para crear el repo y pegar esto?  
¡Avísame y seguimos! 🚀
