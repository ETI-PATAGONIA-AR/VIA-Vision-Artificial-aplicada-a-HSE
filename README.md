# VIA-Vision-Artificial-aplicada-a-HSE
Nuestra aplicacion es un ejemplo claro de como la vision artificial puede personalizarse y optimizarse para aplicaciones reales en seguridad industrial, combinando eficiencia técnica, usabilidad y adaptacion a contextos especificos para mejorar la protección del personal y la gestión de riesgos.

<img width="1365" height="767" alt="0_VIAv1_working" src="https://github.com/user-attachments/assets/d91fb2ad-a95c-45c2-a3d4-861a5f3e2a7d" />

[![Demo en YouTube](https://img.shields.io/badge/▶_Ver_demo-YouTube-red)](https://www.youtube.com/watch?v=7pjkqY5xVAE)

## Resumen del video: Este video no solo presenta el desarrollo y funcionamiento de nuestra aplicación de visión artificial diseñada para detectar el uso correcto de elementos de protección personal (EPP) en ambientes laborales; También mostramos y destacamos las particularidades de entrenar modelos personalizados adaptados a las necesidades específicas de cada empresa, así como las capacidades y limitaciones del sistema actual. Asimismo, se adelantan mejoras futuras en la 2dqa versión basadas en inteligencia artificial.

### 1. Funcionalidad General del Motor de Visión Artificial
La aplicación está enfocada en identificar si el personal en áreas de trabajo utiliza correctamente el EPP, como cascos, antiparras, guantes, mamelucos y calzado de seguridad.
Lo novedoso es que permite crear modelos personalizados basados en videos propios de la empresa, evitando así depender de modelos genéricos que no siempre se adaptan a la indumentaria específica de cada lugar.
Se crea un dataset directamente a partir de videos estáticos de alta calidad para el entrenamiento, sin necesidad de tomar múltiples fotos manualmente.
- El software permite controlar la detección desde una interfaz sencilla con mouse o teclado.
- Parámetros configurables	Umbral de confiabilidad, severidad de faltantes, configuración de capturas y alertas.
- Permite filtrar eventos según si reconoce EPP puestos o faltantes.
- Incorpora un sistema de registro y filtrado automático de eventos, limpiando eventos repetidos o falsos positivos.
- Admite múltiples modelos de vision artificial.
- Soporte multi-cámara y fuentes variadas	Cámaras IP, webcams y videos MP4, con capacidad para hasta 4 cámaras en hardware modesto.
- Integración para exportar datos	Eventos y notas exportables en JSON para sistemas externos.
- Entrenamiento manual y corrección	Posibilidad de añadir clases nuevas y corregir detecciones incorrectas para optimizar el modelo.

<img width="1365" height="718" alt="1_VIAv1_monitores" src="https://github.com/user-attachments/assets/48e7783a-18d4-4276-9b1b-b4100085cb5f" />

<img width="1365" height="718" alt="3_VIAv1_ajustesA" src="https://github.com/user-attachments/assets/142dd029-ef6f-486f-b494-32907582cdec" />

<img width="1365" height="717" alt="3_VIAv1_ajustesB" src="https://github.com/user-attachments/assets/b7cb9aca-b11f-4447-b034-469ab74e06e6" />

<img width="1365" height="717" alt="3_VIAv1_ajustesC" src="https://github.com/user-attachments/assets/ffb1ba96-27b7-4139-b296-c0b7965f0c5b" />

<img width="1365" height="716" alt="3_VIAv1_ajustesD" src="https://github.com/user-attachments/assets/b1069fa5-4c5d-4ae4-8172-446239084076" />

### 2. Configuración y Soporte de Entradas de Video
El software es compatible con múltiples fuentes de video y permite controlar la cantidad de dispositivos según capacidad del hardware, especialmente el procesador y GPU.
- Se pueden agregar cámaras IP con protocolos RTSP o cámaras con web server propio.
- Se aceptan archivos MP4 y feeds de webcam, lo que permite monitorear operadores.
- La recomendación es que las cámaras estén en la misma red cableada o Wi-Fi.
- La limitación principal depende del procesador, siendo preferible tener GPU para mejor rendimiento.

<img width="1365" height="718" alt="3_VIAv1_ajustesA" src="https://github.com/user-attachments/assets/e37ca114-4350-4417-b3e7-7ca942e882dc" />

### 3. Ajustes de Calidad, Severidad y Confiabilidad en la Detección
El sistema permite calibrar varios parámetros para mejorar la precisión y utilidad de las detecciones.

<img width="1365" height="719" alt="2_VIAv1_eventos" src="https://github.com/user-attachments/assets/82396312-8ca9-4086-9cdc-3cb65e7fca90" />

### Parámetro	Descripción:
- Umbral de confiabilidad	Permite ajustar qué nivel de certeza requiere el sistema para aceptar una detección.
- Severidad	Define la gravedad de la falta de un EPP, lo que puede activar alertas o registros especiales.
- Filtros de eventos	Limpia eventos redundantes o falsos positivos basados en lapsos temporales y posturas.
- La severidad puede configurarse para que ciertos faltantes generen capturas o grabaciones automáticas.
El sistema en su segunda version tiene en cuenta la postura y visibilidad de la persona para evitar falsas alarmas,
por ejemplo, cuando la persona está de espaldas o con partes del cuerpo ocultas.

### 4. Construcción y Entrenamiento de Modelos Personalizados
Se explica detalladamente el proceso de entrenamiento de un modelo propio a partir de videos que reflejan la realidad y particularidad de una empresa.
- Se crea una entidad o "empresa" en la aplicación para organizar los datos.

<img width="954" height="534" alt="A_training" src="https://github.com/user-attachments/assets/9c16570a-d67a-41e0-ae6e-9c2827eddc7c" />

- Se carga el video con duración variable, idealmente con más de 200 fotogramas para un buen dataset.

<img width="953" height="534" alt="B_training" src="https://github.com/user-attachments/assets/63c40f21-a873-41e5-b9e7-e7d861be33ae" />
  
- Se aplica un modelo básico para generar detecciones iniciales (cajas delimitadoras) que luego se revisan y corrigen manualmente.

<img width="953" height="534" alt="C_training" src="https://github.com/user-attachments/assets/c50dd1dc-1eef-4920-9863-f5c455df440f" />

- Se pueden crear clases nuevas para elementos específicos que no reconocen los modelos genéricos, por ejemplo, cascos con viseras laterales o modelos particulares de antiparras.
- Cada fotograma es revisado y las detecciones corregidas: quitar falsos positivos y agregar elementos faltantes.
- El proceso entero de generación de un modelo para aproximadamente 300 fotogramas toma alrededor de 60 minutos.

<img width="954" height="540" alt="D_training" src="https://github.com/user-attachments/assets/c7a4527b-2870-4b94-ba01-b004c00f785b" />

<img width="953" height="540" alt="E_training" src="https://github.com/user-attachments/assets/39a7975e-8a04-4cd4-9635-e4d80530a95b" />

<img width="951" height="540" alt="F_training" src="https://github.com/user-attachments/assets/fcb54ce1-3ac9-44fe-9ae9-50eca6631b13" />

<img width="953" height="539" alt="G_training" src="https://github.com/user-attachments/assets/ad0f21ef-a362-4ee6-8895-024fb647f020" />

El modelo resultante ofrece mayor adaptabilidad y precisión para la empresa usuaria; O sea, la personalización del modelo de visión artificial con videos reales de la empresa es crucial para obtener detecciones efectivas y adaptadas al contexto.
La calidad y estabilidad de las cámaras influye directamente en la precisión y reducción de falsos positivos.
El enfoque en filtro inteligente de eventos y uso de índices de confiabilidad mejora la fiabilidad del sistema.
El sistema probado funciona bien incluso con hardware limitado (CPU sin GPU), lo que favorece su escalabilidad.
La integración futura de IA para reconocimiento de posturas marcará un avance significativo en la mejora de la detección y reducción de errores relacionados con visibilidad parcial.
Este motor de visión artificial representa un avance tecnológico importante para mejorar el control automático de seguridad laboral en tiempo real, facilitando la supervisión del cumplimiento de normas de EPP mediante sistemas personalizados y escalables.

### 5. Pruebas y Limitaciones Detectadas
Se muestran pruebas con videos reales que presentan algunos desafíos técnicos.
La cámara en algunos casos se mueve, haciendo que el identificador (ID) de la persona cambie con frecuencia y genere múltiples eventos para una misma persona.
La calidad y estabilidad del video impacta mucho en precisión; videos no profesionales o con rotación producen detecciones erróneas.
Cuando partes del cuerpo quedan fuera del cuadro, el sistema puede erróneamente marcar la ausencia de ciertos EPP, por ejemplo, botas o cascos.
El sistema no detecta antiparras si la persona está de espaldas.
La superposición de modelos genéricos y personalizados puede generar conflictos que se resuelven por prioridad al modelo con mayor índice de confiabilidad.
Se puede ajustar el umbral de detección para hacerlo más estricto o flexible según la calidad del video y las necesidades.

### 6. Uso en Tiempo Real y Gestión de Eventos
Una vez cargados los modelos, la aplicación puede activar la detección en tiempo real sobre múltiples cámaras simultáneamente, hasta 4 cámaras con un CPU Ryzen 7 sin GPU, según lo probado.
Los eventos detectados pueden incluir notas y ser descargados en formato JSON para su integración en otros programas, por ejemplo, para generar reportes o enviar alertas automáticas.
El sistema filtra eventos redundantes o errores de detección para mantener registros claros y útiles.
Permite visualizar en la interfaz separadamente los EPP reconocidos y faltantes para facilitar la supervisión.

### 7. Mejoras Futuras y Próxima Versión
Se anunció una versión 2 en desarrollo que incorporará inteligencia artificial avanzada para el reconocimiento de posturas humanas.
Esto ayudará a:
- Mejorar la interpretación de la posición y partes del cuerpo visibles o cubiertas.
- Reducir falsas alarmas generadas al no poder detectar EPP por ocultación o posición.
- Añadir más funcionalidades basadas en IA para optimizar la detección y análisis de seguridad.

---

### Highlights
🎥 Modelo de visión artificial personalizado basado en videos propios de la empresa.
🦺 Detección eficaz de varios tipos y estilos de EPP, adaptándose a necesidades específicas.
🎯 Filtros inteligentes que reducen alarmas falsas ante escenarios complejos, como postura o bloqueos visuales.
💻 Compatible con múltiples fuentes de video: cámaras IP, archivos MP4 y webcams.
🛠️ Herramienta de entrenamiento y etiquetado interno que permite mejorar continuamente los modelos.
📈 Registro y análisis de eventos con severidad configurable para priorización.
⚙️ Funciona eficazmente con configuraciones estándar de hardware (CPU Ryzen 7 y 8 GB RAM).

### Key Insights
🎯 Adaptabilidad personalizada vs. modelos genéricos
La creación de datasets y modelos a partir de videos reales de la empresa permite resolver problemas comunes en la detección de EPP, como la variabilidad en estilos y colores de cascos o ropa, que los modelos genéricos no contemplan y que pueden generar falsos negativos o positivos.
Esto refleja la importancia de soluciones hechas a medida para contextos industriales específicos.
🤖 Filtros y algoritmo para mejorar la interpretación corporal
La incorporación de inteligencia artificial para discernir posturas y partes del cuerpo, así como para detectar obstáculos que bloqueen la visión (máquinas, personas de espaldas), es crucial para evitar falsas alertas y mejorar la precisión, mostrando un avance notable en la sofisticación de los sistemas de visión artificial para seguridad laboral.
📊 Gestión avanzada de eventos con índices de confiabilidad y severidad
Permitir ajustar umbrales de detección y clasificar la severidad de las faltas brinda un control más granular y permite integrar alertas críticas automáticas, capturar evidencia (fotos o videos) y generar reportes que respalden la gestión de seguridad, facilitando el cumplimiento normativo.
🖥️ Versatilidad en el hardware y entrada múltiple de video
La capacidad de procesar múltiples cámaras en tiempo real solo con CPU, sin necesidad de hardware costoso específico (GPU), facilita la adopción en entornos industriales con recursos limitados, evidenciando eficiencia y optimización en el desarrollo del software.
📚 Proceso iterativo de entrenamiento supervisado
El sistema permite corregir manualmente las detecciones erróneas y agregar nuevas clases de EPP, mejorando así el rendimiento progresivamente.
Este método híbrido (automático + manual) es fundamental para garantizar alta precisión en contextos dinámicos y variados.
🔄 Problemas comunes y retos tecnológicos
La variabilidad del entorno —videos no estáticos, cambios de ID de persona cuando entra y sale del campo visual, calidad variable de imágenes y cuerpos parcialmente visibles— aún representa desafíos relevantes.
El desarrollo apunta a mitigar estos efectos para obtener un sistema robusto y confiable.
📅 Potencial para ampliaciones futuras con IA avanzada
La segunda versión prevista incorpora modelos que detectan no solo presencia o ausencia de EPP, sino también posturas, lo cual permitirá prever comportamientos riesgosos y fortalecer aún más la prevención de accidentes.
Esto destaca el camino hacia soluciones más inteligentes y predictivas en seguridad industrial.

---

## Conclusión
Este video es un ejemplo claro de cómo la visión artificial puede personalizarse y optimizarse para aplicaciones reales en seguridad industrial, combinando eficiencia técnica, usabilidad y adaptación a contextos específicos para mejorar la protección del personal y la gestión de riesgos.

# Venta / Sopporte técnico: 
prof.martintorres@educ.ar
