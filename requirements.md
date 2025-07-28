# Documento de Requerimientos - App y Web Verificadores

## Introducción

El sistema de Verificadores Presenciales es una plataforma tipo marketplace que conecta dos tipos de usuarios, similar al modelo de Uber. La plataforma incluye una página web responsive y dos aplicaciones móviles Android separadas:

- **App Cliente (VerificadoresCliente)**: Para usuarios que necesitan verificar productos antes de comprarlos
- **App Verificador (VerificadoresPro)**: Para profesionales que ofrecen servicios de verificación y quieren generar ingresos

Ambas apps están conectadas a la misma plataforma pero ofrecen experiencias completamente diferentes según el rol del usuario.

## Requerimientos

### Requerimiento 1

**Historia de Usuario:** Como comprador, quiero solicitar una verificación de un producto, para poder comprarlo con confianza conociendo su estado real.

#### Criterios de Aceptación

1. CUANDO el usuario accede al formulario de solicitud ENTONCES el sistema DEBERÁ mostrar campos para categoría, dirección, fecha/hora, descripción y presupuesto
2. CUANDO el usuario completa y envía una solicitud ENTONCES el sistema DEBERÁ validar los datos y crear la solicitud en la base de datos
3. CUANDO se crea una solicitud ENTONCES el sistema DEBERÁ notificar a verificadores disponibles en la zona
4. SI el usuario no completa campos obligatorios ENTONCES el sistema DEBERÁ mostrar mensajes de error específicos

### Requerimiento 2

**Historia de Usuario:** Como comprador, quiero buscar y seleccionar verificadores, para elegir el más adecuado según mi necesidad y presupuesto.

#### Criterios de Aceptación

1. CUANDO el usuario busca verificadores ENTONCES el sistema DEBERÁ mostrar una lista con foto, calificación, especialidades, zona y precio
2. CUANDO el usuario aplica filtros ENTONCES el sistema DEBERÁ mostrar solo verificadores que cumplan los criterios seleccionados
3. CUANDO el usuario selecciona un verificador ENTONCES el sistema DEBERÁ mostrar su perfil completo con estadísticas, opiniones y disponibilidad
4. CUANDO el usuario solicita un verificador ENTONCES el sistema DEBERÁ enviar la solicitud y notificar al verificador

### Requerimiento 3

**Historia de Usuario:** Como verificador, quiero recibir y gestionar solicitudes de trabajo, para poder aceptar trabajos que se ajusten a mi disponibilidad y especialidad.

#### Criterios de Aceptación

1. CUANDO llega una nueva solicitud ENTONCES el sistema DEBERÁ enviar notificación push al verificador
2. CUANDO el verificador ve solicitudes ENTONCES el sistema DEBERÁ mostrar detalles del producto, ubicación, horario y pago propuesto
3. CUANDO el verificador acepta una solicitud ENTONCES el sistema DEBERÁ confirmar la cita y notificar al cliente
4. CUANDO el verificador rechaza una solicitud ENTONCES el sistema DEBERÁ ofrecerla a otros verificadores disponibles

### Requerimiento 4

**Historia de Usuario:** Como verificador, quiero crear informes detallados con fotos, para documentar el estado del producto verificado.

#### Criterios de Aceptación

1. CUANDO el verificador inicia una verificación ENTONCES el sistema DEBERÁ proporcionar herramientas para tomar fotos y notas
2. CUANDO el verificador completa el informe ENTONCES el sistema DEBERÁ validar que incluya fotos, estado general y recomendación
3. CUANDO se envía el informe ENTONCES el sistema DEBERÁ notificar al cliente y generar PDF descargable
4. SI faltan elementos obligatorios ENTONCES el sistema DEBERÁ impedir el envío y mostrar qué falta

### Requerimiento 5

**Historia de Usuario:** Como usuario (cliente o verificador), quiero comunicarme en tiempo real, para coordinar detalles de la verificación.

#### Criterios de Aceptación

1. CUANDO se confirma una verificación ENTONCES el sistema DEBERÁ habilitar chat entre cliente y verificador
2. CUANDO se envía un mensaje ENTONCES el sistema DEBERÁ entregarlo en tiempo real y enviar notificación si el destinatario está offline
3. CUANDO el verificador está en camino ENTONCES el sistema DEBERÁ permitir compartir ubicación en tiempo real
4. CUANDO se completa la verificación ENTONCES el sistema DEBERÁ cerrar el chat automáticamente después de 24 horas

### Requerimiento 6

**Historia de Usuario:** Como usuario, quiero ver verificadores y solicitudes en un mapa en tiempo real, para entender la actividad en mi zona.

#### Criterios de Aceptación

1. CUANDO el usuario accede al mapa ENTONCES el sistema DEBERÁ mostrar verificadores activos y solicitudes pendientes con marcadores diferenciados
2. CUANDO el usuario filtra por categoría ENTONCES el sistema DEBERÁ mostrar solo elementos de esa categoría
3. CUANDO el usuario hace clic en un marcador ENTONCES el sistema DEBERÁ mostrar información detallada en popup
4. CUANDO hay solicitudes urgentes ENTONCES el sistema DEBERÁ destacarlas con animaciones y colores especiales

### Requerimiento 7

**Historia de Usuario:** Como verificador, quiero gestionar mi perfil profesional, para mostrar mis especialidades, zona de cobertura y tarifas.

#### Criterios de Aceptación

1. CUANDO el verificador edita su perfil ENTONCES el sistema DEBERÁ permitir actualizar especialidades, zonas, horarios y precios
2. CUANDO se actualiza el perfil ENTONCES el sistema DEBERÁ validar la información y guardar los cambios
3. CUANDO el verificador sube documentos de certificación ENTONCES el sistema DEBERÁ marcar el perfil como "Verificado"
4. CUANDO el verificador cambia su disponibilidad ENTONCES el sistema DEBERÁ actualizar su visibilidad en búsquedas

### Requerimiento 8

**Historia de Usuario:** Como usuario, quiero calificar y opinar sobre verificadores, para ayudar a otros usuarios y mejorar la calidad del servicio.

#### Criterios de Aceptación

1. CUANDO se completa una verificación ENTONCES el sistema DEBERÁ solicitar calificación y opinión al cliente
2. CUANDO el usuario envía una calificación ENTONCES el sistema DEBERÁ actualizar el promedio del verificador
3. CUANDO se publica una opinión ENTONCES el sistema DEBERÁ mostrarla en el perfil del verificador
4. SI una calificación es muy baja ENTONCES el sistema DEBERÁ alertar al equipo de soporte

### Requerimiento 9

**Historia de Usuario:** Como administrador, quiero gestionar usuarios y verificadores, para mantener la calidad y seguridad de la plataforma.

#### Criterios de Aceptación

1. CUANDO se registra un nuevo verificador ENTONCES el sistema DEBERÁ requerir verificación de identidad y documentos
2. CUANDO hay reportes de usuarios ENTONCES el sistema DEBERÁ permitir investigar y tomar acciones
3. CUANDO un verificador tiene calificaciones consistentemente bajas ENTONCES el sistema DEBERÁ permitir suspender su cuenta
4. CUANDO se detecta actividad sospechosa ENTONCES el sistema DEBERÁ generar alertas automáticas

### Requerimiento 10

**Historia de Usuario:** Como usuario, quiero acceder a la plataforma desde web y móvil, para usar el servicio desde cualquier dispositivo.

#### Criterios de Aceptación

1. CUANDO el usuario accede desde web ENTONCES el sistema DEBERÁ mostrar una interfaz responsive que funcione en desktop, tablet y móvil
2. CUANDO el usuario usa la app móvil ENTONCES el sistema DEBERÁ proporcionar funcionalidades nativas como GPS, cámara y notificaciones push
3. CUANDO el usuario cambia de dispositivo ENTONCES el sistema DEBERÁ sincronizar datos automáticamente
4. CUANDO no hay conexión ENTONCES la app móvil DEBERÁ permitir funcionalidad offline básica