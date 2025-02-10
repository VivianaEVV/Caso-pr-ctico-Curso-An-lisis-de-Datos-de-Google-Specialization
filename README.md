# Caso Práctico Curso Análisis de Datos de Google Specialization

## Tarea Empresarial: Análisis de Usuarios en Cyclistic

---

## 1. Instrucción de la Tarea Empresarial

### Objetivo
Determinar en qué se diferencian los **socios anuales (miembros)** y los **ciclistas ocasionales** (usuarios de pases diarios o de un solo viaje) en el uso de las bicicletas de Cyclistic. El análisis se centrará en aspectos como:
- **Duración de los viajes**
- **Distribución por días de la semana**
- **Horas pico**
- **Estaciones utilizadas**

Con esta información se podrán diseñar estrategias de marketing específicas para fomentar la conversión de los usuarios ocasionales en miembros anuales, incrementando así la rentabilidad del sistema.

### Contexto y Antecedentes

#### Sobre Cyclistic
Cyclistic es un sistema de bicicletas compartidas operado en Chicago. Ofrece una amplia variedad de bicicletas, incluyendo opciones eléctricas y bicicletas adaptadas. Cuenta con diferentes planes de precios: pases de un solo viaje, pases diarios y membresías anuales.

#### Rentabilidad y Estrategia de Marketing
- **Miembros anuales:** Son significativamente más rentables para la empresa.
- **Usuarios ocasionales:** La flexibilidad de los planes de precios ha permitido captar un gran número de ciclistas ocasionales, pero su rentabilidad es menor.

#### Rol de la Dirección
La directora de marketing, **Lily Moreno**, ha identificado la necesidad de aumentar el número de membresías anuales para garantizar el éxito futuro del negocio. Para ello, es esencial comprender las diferencias en el comportamiento de ambos grupos de usuarios y desarrollar campañas de marketing efectivas y personalizadas que impulsen la conversión de usuarios ocasionales a miembros.

### Preguntas Clave a Responder

#### Diferencias en el Uso
- **Duración de los viajes:** ¿Cómo varía la duración de los viajes entre miembros y usuarios ocasionales?
- **Frecuencia de uso:** ¿Existen diferencias en la frecuencia de uso, días de la semana o en las horas pico de cada grupo?
- **Estaciones:** ¿Se observa alguna tendencia en cuanto a las estaciones de inicio y finalización de los viajes?

#### Motivar para la Conversión
- ¿Qué patrones o comportamientos en el uso de las bicicletas podrían ser indicativos de la disposición de los usuarios ocasionales a pasar a una membresía anual?

#### Oportunidades en Medios Digitales
- ¿Qué oportunidades ofrece el entorno digital (por ejemplo, redes sociales, correo electrónico, campañas online) para influenciar y persuadir a los usuarios ocasionales a convertirse en miembros anuales?

---

## 2. Fuentes de Datos Utilizadas

### Datos Históricos de Viajes de Cyclistic
Para este análisis se han utilizado los datos históricos correspondientes a los **últimos 12 meses** de viajes realizados en el sistema de bicicletas compartidas de Cyclistic. Los datos fueron proporcionados en archivos en formato **CSV**, los cuales contienen información detallada de cada viaje.

### Contenido de los Datos
- **ID del Viaje:** Un identificador único para cada viaje (originalmente denominado `trip_id`).
- **Fecha y Hora de Inicio:** Registro del momento en el que inicia el viaje (columna `started_at`).
- **Fecha y Hora de Fin:** Registro del momento en el que finaliza el viaje (columna `ended_at`).
- **Tipo de Usuario:** Información que permite diferenciar entre usuarios con membresía anual (miembros) y usuarios que utilizan pases de un solo viaje o diarios (ciclistas ocasionales).
- **Información de Estaciones:** Datos relativos a la estación de origen y la estación de destino, incluyendo nombres y, en algunos casos, identificadores y coordenadas geográficas (latitud y longitud).
- **Otras Variables:** En algunos archivos se incluyen detalles adicionales como el tipo de bicicleta utilizada (por ejemplo, bicicleta eléctrica o tradicional).

### Consideraciones de Privacidad y Calidad
- **Privacidad:**  
  No se utilizará ninguna información personal identificable, garantizando el cumplimiento de las normas de privacidad y protección de datos.

- **Integridad y Actualidad:**  
  Se verificó que los datos sean actuales, completos y de origen confiable.

- **Formato y Consistencia:**  
  Los datos se han revisado y validado para asegurar que se encuentren en el formato correcto para el análisis. Además, se realizó una copia de seguridad de los archivos originales para preservar la información sin alterar y facilitar futuras consultas o validaciones.

---

## 3. Documentación de la Limpieza y Manipulación de Datos

Para asegurar la calidad y coherencia del análisis, se siguieron los siguientes pasos en el proceso de preparación y limpieza de los datos:

### Descarga y Organización

#### Descarga de Datos
- Se descargaron los 12 meses de datos históricos de viajes de Cyclistic en archivos CSV.

#### Organización de Archivos
- Se creó una carpeta principal, que contiene subcarpetas organizadas por tipo de archivo:
  - **Archivos Originales:** Carpeta con los archivos en formato CSV.
  - **Copia Archivos:** Carpeta con los archivos copiados.
- Esta estructura permitió mantener una copia de seguridad de la información original, evitando alteraciones accidentales durante el procesamiento.

### Conversión y Estandarización

#### Conversión de Formatos
- Cada archivo fue abierto y guardado en el formato adecuado, garantizando un formato homogéneo para facilitar el análisis.

#### Estandarización de Columnas
- Se verificó que las columnas de cada archivo tengan el mismo formato y nomenclatura, lo que permitió la concatenación de los archivos sin pérdida de información o discrepancias en los tipos de datos.

### Creación de Nuevas Variables

#### `ride_length` (Duración del Viaje)
- Se creó la variable `ride_length` calculando la diferencia entre la fecha y hora de finalización (`ended_at`) y la fecha y hora de inicio (`started_at`).
- Posteriormente, se aplicó un formato de tiempo (HH:MM:SS) para representar de forma clara la duración de cada viaje.

#### `day_of_week` (Día de la Semana)
- Se generó la variable `day_of_week` utilizando la función `WEEKDAY` (por ejemplo, en Excel: `=WEEKDAY(C2,1)`), que extrae el día de la semana a partir de la fecha de inicio del viaje.
- Se verificó que, según la función utilizada, el número **1** corresponde al domingo y el número **7** al sábado.

### Verificación y Limpieza Adicional

#### Revisión de Duplicados y Valores Faltantes
- Se inspeccionó el conjunto de datos para identificar y eliminar registros duplicados o entradas incompletas.
- En el caso de valores faltantes, se procedió a imputarlos (por ejemplo, rellenando con “Desconocido” en campos de texto) o a eliminar registros cuando fuera crítico para el análisis.

#### Corrección de Errores en Fechas y Horas
- Se revisaron y corrigieron posibles errores en los formatos de fecha y hora, eliminando milisegundos innecesarios.
- Se aseguró que las conversiones a tipo `datetime` fueran exitosas y que la fecha de inicio fuese siempre anterior a la fecha de finalización.

### Documentación de Cambios y Versiones

#### Registro de Cambios
- Cada paso del proceso de limpieza y transformación fue documentado.

#### Versiones de Respaldo
- Se guardaron versiones de respaldo de los datos originales y de los conjuntos transformados para poder realizar revisiones o comparaciones posteriores, garantizando la trazabilidad y reproducibilidad del proceso.

---

## 4. Resumen del Análisis

### Exploración Inicial

El análisis inicial consistió en obtener estadísticas descriptivas para obtener una visión general del comportamiento de los miembros y ciclistas ocasionales en el uso de las bicicletas Cyclistic. Se realizó un análisis de los siguientes puntos:

- **Promedio, Máximo y Mínimo de `ride_length` para cada grupo**:  
  Se calculó la duración promedio de los viajes (`ride_length`) para los dos grupos de usuarios: miembros y ocasionales. Se compararon también los valores máximos y mínimos para observar si existen diferencias notables en la duración de los viajes entre los dos grupos.
- df['ride_length'] = (df['ended_at'] - df['started_at']).dt.total_seconds() / 60  # En minutos

- **Recuento de Viajes por Día de la Semana y por Tipo de Usuario**:  
  Se contabilizó la cantidad de viajes realizados por día de la semana para cada tipo de usuario. Esto permitió identificar si ciertos días tienen una mayor o menor demanda, así como la preferencia de los usuarios por ciertos días de la semana (por ejemplo, fines de semana vs. días laborales).
- summary = df.groupby('user_type')['ride_length'].describe()

### Análisis Detallado

- **Comparación de Duración de Viajes**:  
  Se utilizó una tabla dinámica para calcular la duración promedio de los viajes para ambos grupos (miembros vs. ocasionales). Se observaron diferencias en la duración de los viajes, sugiriendo que los miembros tienden a realizar viajes más cortos y frecuentes, mientras que los ciclistas ocasionales tienen viajes más largos, a menudo asociados a recorridos recreativos o de ocio.

- **Patrones Temporales**:  
  Se analizó la distribución de los viajes a lo largo de la semana, identificando patrones de comportamiento que muestran diferencias entre días laborales y fines de semana. Los miembros parecen usar las bicicletas con más regularidad durante la semana, mientras que los ciclistas ocasionales se concentran más en los fines de semana, lo que podría estar relacionado con actividades recreativas.

- **Tendencias y Picos**:  
  Se identificaron las horas pico durante el día y las estaciones con mayor demanda, lo que permitió observar la variabilidad en la utilización de bicicletas en diferentes momentos del día. Además, se detectaron picos de demanda en ciertos horarios (por ejemplo, por la mañana temprano o al final de la tarde), lo cual es consistente con patrones de movilidad en la ciudad.

### Hallazgos Clave

- **Comportamiento de los Miembros vs. Ocasionales**:  
  Los miembros tienden a utilizar las bicicletas de manera más regular y frecuente, con viajes más cortos, a menudo de naturaleza utilitaria (por ejemplo, desplazamientos diarios o para ir al trabajo). En contraste, los ciclistas ocasionales tienen viajes más largos y esporádicos, relacionados probablemente con actividades de ocio.

- **Diferencias Geográficas o de Uso**:  
  Se observaron diferencias en el uso de las estaciones, con algunas ubicaciones teniendo una mayor concentración de viajes tanto para miembros como para ciclistas ocasionales. Sin embargo, ciertos lugares parecen atraer más a los ciclistas ocasionales, mientras que las estaciones en zonas de trabajo o comerciales tienen más actividad por parte de los miembros.

- **Oportunidades de Marketing**:  
  A partir de los hallazgos, se podrían diseñar estrategias de marketing dirigidas a promover las membresías en momentos específicos, como en días de baja demanda o en estaciones con menor tráfico. Por ejemplo, se podrían ofrecer descuentos o promociones especiales para nuevos miembros en días con menos viajes o en zonas geográficas donde los ciclistas ocasionales sean más frecuentes. Además, podrían promoverse planes de membresía con beneficios adicionales durante las horas pico para fidelizar a los usuarios que ya utilizan las bicicletas.

