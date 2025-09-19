# pruebaValetFlowQR
Se busca una solución digital que elimina el uso de papel, mejorando la experiencia del cliente al usar un servicio de valet parking, el cual plantea aumentar la eficiencia operativa mediante el uso de códigos QR, inteligencia artificial, Internet de las Cosas, chatbots y herramientas de automatización.


# INVESTIGACIóN
# ValetFlow QR – Arquitectura de la App

## Contexto del proyecto
Aplicación móvil para la gestión de valet parking sin papel mediante QR.  
- *Clientes B2B*: hoteles, restaurantes, bares, centros comerciales y empresas de outsourcing.  
- *Usuarios finales*: clientes de nivel medio-alto y alto que buscan rapidez y seguridad.  
- *Fuentes de datos*: API REST (propietaria), posible uso de Firestore para tiempo real.  
- *Notificaciones*: Firebase Cloud Messaging.  
- *Escalabilidad*: integración futura con IA (predicción de picos, reconocimiento de daños) e IoT.

## Arquitectura seleccionada
*MVVM con inspiración en Clean Architecture, usando **Riverpod* para gestión de estado.  
- Separación en capas: presentation, domain, data.  
- Regla de dependencia: capas externas dependen de Domain, nunca al revés.  

## Estructura de carpetas

## Riesgos identificados
- *Sobrecarga en ViewModels* → se mitiga usando casos de uso.
- *Dependencia fuerte de un gestor de estado* → mitigación: aislar la lógica de negocio.
- *Complejidad en integración de múltiples clientes B2B* → repositorios modulares.

## Pruebas previstas
- *Unit tests*: casos de uso y lógica en ViewModels.
- *Repository tests*: validación de integración con API y cache (con mocks).
- *Widget tests*: validación de UI (render de estados loading, success, error).
- *Integration tests*: flujo completo de “ingreso ticket → notificación → entrega vehículo”.
