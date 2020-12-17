 
1.	Introducción 
 
En este documento se planea detallar las características principales que serán aplicadas a un sistema de software que gestionara servicios de altas, bajas y cambios de productos 
mediante la aplicación de estilos arquitectónicos REST y microservicios para un sistema de dulcería solicitado por el cliente Sergio Mena Zamora que desea “entrar en vanguardia” con un sistema para innovar su negocio e incrementar sus ventas. 
      1.1 Contexto de Negocio            
 1.1.1 Antecedentes 
 
A lo largo su vida laboral nuestro cliente ha realizado la compra de productos de dulcería, que normalmente no es capaz gestionar formalmente al momento de realizar un “corte de caja” que detallen las ventas diarias y mensuales, que contribuyan a definir periodos donde le “va mejor” entre meses, adicionalmente desconoce la cantidad de productos que mensualmente ingresan o salen de su tienda, dejando en cuestión si es un negocio “rentable” para él. 
El tiempo de renovación de sus productos es mensual, por lo que la información que expresen los números después de cada mes requerirá compararlos con los anteriores para determinar los productos que son mas vendidos “por temporada” a lo largo del año. 
1.1.2 Fase del problema 
 
•	Complicaciones para identificar existencia de un producto en stock. 
•	Falta de registro en la entrada y salida de mercancía.  
•	Falta de registro para las ventas mensuales. 
•	Conflictos para distinguir productos con mayor demanda en un día / mes. 
•	No hay facilidad de dar seguimiento a productos con mayor demanda en ciertas temporadas del año. 
•	Falta de registro para el catálogo de productos menos vendidos. 
•	Falta de registro para el catálogo de productos más vendidos. 
•	Muchos de los productos que adquiere (La mayoría), llevan un tiempo limitado de caducidad, al permanecer mayor tiempo en almacén representará un riesgo de pérdida.  
 
 
1.1.3 Objetivos de negocio 
 
ID 	DESCRIPCIÓN DE LOS OBJETIVOS DE NEGOCIO 
ON-1 	Generar historial en ventas diarias. 
ON-2 	Incrementar ventas al identificar si existen productos o no en stock. 
ON-3 	Detectar artículos en stock más solicitados. 
ON-4 	Detectar artículos en stock menos solicitados. 
ON-5 	Agilizar entrada y salida de productos para evitar caduquen 
ON-6 	Mitigar desorden entre los productos del negocio 
ON-7 	Reducir pérdidas de productos que caducan en almacén por falta de ventas. 
ON-8 	Generar un sistema para controlar entrada / salida de productos  
 
1.2. Visión de la Solución 
 
Se pretende realizar el sistema cubriendo cada uno de los problemas puntualizados previamente 
(fase del problema), la dirección pendular para el desarrollo del proyecto requiere la implementación de un orden de catálogos para todos los productos, así también para las ventas que puedan ser realizadas mensualmente. 
1.2.1 Fase de visión 
 
Para llevar a cabo lo mencionado anteriormente, se considerará implementar es uso de servicios REST y microservicios que contribuyan la integridad funcional del sistema, en un entorno de petición / respuesta según la tarea requerida por el usuario final del sistema. Aplicando servicios entre un cliente y servidor las solicitudes como consulta, actualización, alta, y baja de productos realizadas por el usuario, tendrán soporte mediante un sistema de base de datos para el registro de cada producto. 
 
 
 
 
 
 
 
 
 
 
 
 
 
1.2.2. Características del sistema 
 
ID 	CARACTERÍSTICA 	PRIORIDAD 	OBJETIVO DE NEGOCIO 
CAR-1 	El sistema deberá establecer un orden para el catálogo de dulces 	ALTA 	ON-6, ON-8 
CAR-2 	El sistema deberá aplicar un sistema de registro de ventas diario guardando la fecha y la hora de venta. 	ALTA 	ON-1, ON-3 
CAR-3 	El sistema deberá aplicar un registro de la cantidad de elementos vendidos mensualmente. 	ALTA 	ON-3 
CAR-4 	El sistema deberá categorizar los dulces con menor tiempo de caducidad. 	MEDIA 	ON-5, ON-7 
CAR-5 	El sistema deberá notificar en pantalla los productos con mayor tiempo en stock (Para evitar compras adicionales del producto). 	MEDIA 	ON-7, ON-4 
CAR-6 	Implementar consulta de productos de productos en stock. 	ALTA 	ON-2 
CAR-7 	Implementar alta de nuevos productos de productos en stock. 	ALTA 	ON-8 
CAR-8 	Implementar baja de productos de productos en stock. 	ALTA 	ON-8 
CAR-9 	Implementar actualización por cantidad de productos en stock. 
 	ALTA 	ON-8 
CAR 10 	El sistema deberá notificar 
mensualmente los artículos con menor demanda 	MEDIA 	ON-4 
 
 
 
 
 
 
 
 
1.3. Alcance 
 
NÚMERO DE ENTREGA 	TEMA PRINCIPAL 	ID CARACTERÍSTICA 
1.0 	Ordenamiento de productos (Funcionalidad Básica). 	CAR-1, CAR-4 
2.0 	Registro de ventas (Funcionalidad Básica). 	CAR-2, CAR-3 
3.0 	Actividades CRUD (Funcionalidad Básica) 	CAR-6, CAR-7, CAR-8, CAR-9 
4.0 	Notificaciones Importantes          (Funcionalidad Complementaria) 	CAR-5, CAR-10 
 
1.4.	Contexto del sistema 
 
NOMBRE DEL SISTEMA 	SIGLAS DEL PROYECTO 
Sistema Gestor de Dulces 1.0 	SGD-V1 
 
1.4.1	Interesados 
 
NOMBRE 	DESCRIPCIÓN 		RESPONSABILIDAD 
Cliente 	Interesado en desarrollo del sistema. 	• 	 
Proporcionar calendario de entrega. 
		• 	Determinar límite de recursos. 
		• 	Define cambios de última hora. 
		• 
 	Aceptación de proyecto. 
Arquitecto de Software 	Elemento esencial del equipo de desarrollo. 	• 	 
Determina diseño de la arquitectura por aplicar.  
		• 	Notificará cualquier cambio en la decisión de la implementación del sistema a otros integrantes del equipo de desarrollo. 
		• 	Validación de Requerimientos   
 
Desarrollador Front-End 	Equipo de desarrollo enfocado a la 
implementación de una interfaz gráfica digital mediante uso de 
herramientas HTML y CSS. 	• 
• 
• 	 
Desarrollo de elementos de interacción o vistas “intuitivas” dentro del sistema. 
Generación de diseños de estilos propios. Asignación de elementos representativos del negocio 	del 	cliente 	(logos 	o 	fuentes representativas del negocio, color, etc). 
Desarrollador Back-End 	Equipo de desarrollo enfocado a la 
implementación de factores lógicos del sistema. 	• 	Encargados de desarrollar elementos funcionales elementales para la arquitectura básica dentro del sistema junto a funcionalidades complementarias adicionales. 
 
		• 	Desarrollo o uso de componentes que se acoplen a la arquitectura que sea implementada. 
 
		• 	Implementación de tecnología REST 
 
		• 	Implementación de microservicios para solicitudes del sistema. 
 
Administradores de la Base de 
Datos 	Equipo de desarrollo enfocado a la 
implementación del sistema de 
almacenamiento de la información. 	• 
• 
 
 	Encargados de gestionar y administrar la información que contendrá la base de datos en el sistema. 
Administrar la información mediante un sistema de consultas  
 
o CREACION o CONSULTA o ACTUALIZACION o BAJA  
 
 
 
 
 
 
 
 
 
 
 
 
1.4.2. Diagrama de contexto 
 
 
  
 
 
 
 
 
 
 
 	 	1.4.3. Entorno de operación 
 
Las especificaciones técnicas mínimas (Hardware) para una ejecución optima del sistema son las siguientes: 
o	Procesador AMD A4-3300M APU / Radeon HD Graphics (2 CPU´s – 1.9GHz).  
o	4GB Memoria RAM o APU AMD Radeon HD 6480G 
Requerimientos Mínimos (Software) para uso óptimo del sistema. 
o	S.O. Windows 7 Ultimate 64 Bits.  o Navegador Google Chrome ver, Firefox, Opera. 
o	MySQL ver. 8.0.22 o Spring Framework – Spring Boot o Jdk 15.0.1 o NetBeans 8.2 
 
1.5. Información adicional. 
  1.5.1 Criterios de aceptación. 
 
Para la aceptación del proyecto serpa requerido sean cubiertos los siguientes elementos: 
•	Entrega Funcional del sistema solicitado “Sistema Gestor de Dulces”. 
•	Aplicación de las arquitecturas REST y uso de micro servicios en el desarrollo del sistema. 
•	Entrega completa y clara de la documentación del sistema junto a los correspondientes diagramas. 
•	Entrega en el tiempo y fecha preestablecidos por el cliente (docente). 
•	El sistema deberá ser capaz de medir aplicando pruebas unitarias / integración. 
 
