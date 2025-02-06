# Caso practico Curso Analisis de Datos de Google Specialization
# Tarea Empresarial: Análisis de Usuarios en Cyclistic

## 1. Instrucción de la Tarea Empresarial

### Objetivo
Determinar en qué se diferencian los **socios anuales (miembros)** y los **ciclistas ocasionales (usuarios de pases diarios o de un solo viaje)** en el uso de las bicicletas de Cyclistic. El análisis se centrará en aspectos como:

- Duración de los viajes
- Distribución por días de la semana
- Horas pick
- Estaciones utilizadas

Con esta información se podrán diseñar **estrategias de marketing específicas** para fomentar la conversión de los usuarios ocasionales en miembros anuales, incrementando así la rentabilidad del sistema.

### Contexto y Antecedentes

#### Sobre Cyclistic
- Cyclistic es un sistema de bicicletas compartidas operado en Chicago.
- Ofrece una amplia variedad de bicicletas, incluyendo opciones eléctricas y bicicletas adaptadas.
- Cuenta con diferentes planes de precios: pases de un solo viaje, pases diarios y membresías anuales.

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

## 2. Fuentes de Datos Utilizadas

### Datos Históricos de Viajes de Cyclistic

Para este análisis se han utilizado los datos históricos correspondientes a los **últimos 12 meses** de viajes realizados en el sistema de bicicletas compartidas de Cyclistic. Los datos fueron proporcionados en archivos en formato **CSV**, los cuales contienen información detallada de cada viaje.

#### Contenido de los Datos

- **ID del Viaje:**  
  Un identificador único para cada viaje (originalmente denominado `trip_id`).

- **Fecha y Hora de Inicio:**  
  Registro del momento en el que inicia el viaje (columna `started_at`).

- **Fecha y Hora de Fin:**  
  Registro del momento en el que finaliza el viaje (columna `ended_at`).

- **Tipo de Usuario:**  
  Información que permite diferenciar entre usuarios con membresía anual (miembros) y usuarios que utilizan pases de un solo viaje o diarios (ciclistas ocasionales).

- **Información de Estaciones:**  
  Datos relativos a la estación de origen y la estación de destino, incluyendo nombres y, en algunos casos, identificadores y coordenadas geográficas (latitud y longitud).

- **Otras Variables:**  
  En algunos archivos se incluyen detalles adicionales como el tipo de bicicleta utilizada (por ejemplo, bicicleta eléctrica o tradicional).

### Consideraciones de Privacidad y Calidad

- **Privacidad:**  
  No se utilizará ninguna información personal identificable, garantizando el cumplimiento de las normas de privacidad y protección de datos.

- **Integridad y Actualidad:**  
  Se verificó que los datos sean actuales, completos y de origen confiable.

- **Formato y Consistencia:**  
  Los datos se han revisado y validado para asegurar que se encuentren en el formato correcto para el análisis. Además, se realizó una copia de seguridad de los archivos originales para preservar la información sin alterar y facilitar futuras consultas o validaciones.
