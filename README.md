# ProyectoFinal_PDI_DeteccionDePlacas
# Sistema de Detección Automática de Placas Vehiculares + Lectura de Texto (OCR)

**Proyecto Final – Procesamiento Digital de Imágenes (2025-2)**  
Universidad Nacional de Colombia – Juan Esteban López (Juaano28)

## 1. Problema real que resolvemos
En parqueaderos de universidades, conjuntos residenciales y centros comerciales en Colombia se generan largas filas porque:
- El guardia debe identificar visualmente la placa.
- En muchos casos aún se registra manualmente.
- Esto genera congestión, pérdida de tiempo y errores humanos.

**Solución propuesta**: Un sistema de visión por computadora que:
1. Detecta automáticamente la ubicación exacta de la placa vehicular (YOLOv11).
2. Lee el texto de la placa en tiempo real (EasyOCR).
3. Es rápido, preciso y desplegable en entornos reales (incluyendo dispositivos móviles).

## 2. Tareas de visión por computadora
- **Detección de objetos (Object Detection)** → YOLOv11m (1 clase: `license_plate`)
- **Reconocimiento Óptico de Caracteres (OCR)** → EasyOCR (lectura de texto en placa recortada)

## 3. Objetivos del proyecto
**General**  
Desarrollar e implementar un sistema completo de detección y lectura de placas vehiculares basado en YOLOv11 + EasyOCR, rápido, preciso y desplegable.

**Específicos**  
- Alcanzar mAP@0.5 ≥ 0.95 en validación  
- Exportar el modelo a TensorFlow Lite (LiteRT) con mínima pérdida de precisión  
- Implementar inferencia local con OCR  
- Desplegar aplicación web funcional (subida de foto + webcam)  
- Demostrar funcionamiento en tiempo real

**Resultados alcanzados**  
| Métrica              | Valor    |
|----------------------|----------|
| mAP@0.5              | 97.6%   |
| mAP@0.5:0.95         | 72.3%   |
| Precision            | 98.78%  |
| Recall               | 94.76%  |
| Tamaño original (.pt)| 38.6 MB |
| Tamaño LiteRT (int8) | 19.7 MB (51% del original) |

## 4. Dataset utilizado
**Principal**  
- Dataset: [License Plate Recognition](https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e/dataset/4)
- ~10.000 imágenes con augmentations (lluvia, noche, blur, etc.)
- 1 clase: `license_plate`
- Formato YOLOv11
- Enlace público: https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e

**Extra**  
- Imágenes propias capturadas en parqueaderos colombianos (para futuras mejoras de robustez local).

## 5. Tecnologías y herramientas
| Etapa               | Tecnología / Librería              | Detalle                  |
|---------------------|------------------------------------|--------------------------|
| Modelo              | Ultralytics YOLOv11                | yolo11m                  |
| Framework           | PyTorch                            | 2.4+                     |
| OCR                 | EasyOCR                            | 1.7.1 (español)          |
| Entrenamiento       | Kaggle Notebook (GPU)              | -                        |
| Exportación         | TensorFlow Lite (int8)             | -                        |
| Inferencia local    | Python + OpenCV + Streamlit        | -                        |
| Despliegue          | Streamlit Cloud (app web con webcam)| Gratis y permanente      |
| Control de versiones| Git + GitHub                       | -                        |

## 6. Enlaces importantes
- Repositorio GitHub: https://github.com/Juaano28/ProyectoFinal_PDI_DeteccionDePlacas
- Dataset en Roboflow: https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e
- Modelo entrenado (.pt): https://drive.google.com/file/d/1aXBGNtZn3Xe01iv-_I0JdVp_XEBHc-U5/view?usp=sharing
- Modelo LiteRT (.tflite): [En carpeta Drive]
- Carpeta completa del proyecto (modelos, gráficas, resultados): https://drive.google.com/drive/folders/1DAiyY98AsRaeyaU6jO5yB-wK78dygjjR?usp=drive_link
- App web en vivo (Streamlit Cloud): [Pendiente – agregar al finalizar despliegue]

## Instalación y uso local
```bash
pip install ultralytics easyocr streamlit opencv-python-headless
streamlit run app.py
