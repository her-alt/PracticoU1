UNIDAD 1 - ENTREVISTA EN ESPAÑOL Y DIAGRAMA UML PARA EL INICIO DEL PROYECTO
==============================================

# Proyecto de Curso: Sistema de Alquiler y gestión de casas

Este proyecto surge como caso de estudio para la materia **Base de Datos 1** de la carrera de *Ingeniería Informática* en la 
**Universidad Autónoma Gabriel Rene Moreno (UAGRM)**. El objetivo principal es realizar el diseño conceptual, lógica y fisica de un
Base de Datos que resuelva los problemas de gestión, control y registro de la información de alquiler de casas, de un propietario
o empresa de alquiler de viviendas.

## 📋 Transcripción de la Entrevista del Dueño de Alquiler de Casas

*   **Entrevistador:** Estudiante de Ingeniería Informática (UAGRM)
*   **Entrevistado:** Hernan Fernandez/Dueño de la casa en alquiler

---

## 🏠 Sistema de alquiler y gestión de casas
# Narración del cliente 
> "Soy Hernan Fernandez Necesito llevar un registro de los lugares, de las personas que las alquilan y de los contratos
> Quiero registrar los datos de cada casa, como su dirección, zona, número de habitaciones, precio mensual y estado.
> También necesito saber quién está alquilando cada casa, desde qué fecha hasta qué fecha y si realizó el pago correspondiente. Además,
> quiero poder consultar qué casas están disponibles y cuáles están alquiladas”

## Problema Principal
Quiero registrar los datos de cada casa, como su dirección, zona, número de habitaciones, precio mensual y estado.
También necesito saber quién está alquilando cada casa, desde qué fecha hasta qué fecha y si realizó el pago correspondiente. Además,
quiero poder consultar qué casas están disponibles y cuáles están alquiladas.

## Objetivo Principal
Desarrollar una base de datos relacional para ayudar al empresario a gestionar de manera organizada la información de sus clientes,
las casas disponibles y ocupadas, así como el registro y seguimiento de los pagos correspondientes a cada alquiler.

**Registrar** la información personal de los clientes de manera organizada.

**Registrar y controlar** las casas disponibles y ocupadas, incluyendo sus características y datos relevantes.

**Relacionar** cada cliente con la casa que tiene alquilada.

**Registrar los pagos** realizados por cada cliente, incluyendo fecha, monto y periodo correspondiente.

**Consultar** el estado de moderno de la casa que desee con la informacion y detalles correspondientes.

**Facilitar la administración** de la informaci+on mediante un sistema que permita realizar consultas y actualizar 
los registros de manera sencilla.

**Suposiciones:**

* El inquilino se identifica por su CI.
* Cada casa tiene una dirección única.
* Un contrato pertenece a un solo inquilino y una sola casa.
* Un contrato puede tener muchos pagos.

---

# Entidades y atributos

**PROPIETARIO**
* id_propietario
* CI
* Nombre
* Apellido
* Telefono

**CASA**
* id_casa
* habitaciones
* baño
* precio_de_venta
* estado_de_casa
* numero_de_pisos
* garaje
* dirección
* ciudad
* zona
 
**INQUILINO**
* id_inquilino
* CI
* Nombre
* Apellido
* Teléfono
 

**CONTRATO**
* id_contrato 
* Fecha_inicio
* Fecha_fin
* precio_acordado
* plazo_pago
* estado
* forma_pago
* observaciones
* id_propietario
* id_cliente
* id_casa

**PAGO**
* id_pago
* id_contrato
* fecha_pago
* monto
* metodo_pago
* estado_pago
* numero_pago

# Relaciones

# Unidad V : Normalización y Dependencias Funcionales

1. Claves Candidatas y Dependencias Funcionales

| Entidad | Clave candidata |
|------|---------------|
| Propietario | id_propietario |
| Cliente | id_cliente |
| Casa | id_casa |
| Contrato | id_contrato |
| Pago | id_contrato |
| Cuota | nro_cuota |

**Primer Forma Normal (1NF)**

**PROPIETARIO**
| ID_Propietario | CI | Nombre | Apellido | Telefono |
|------|------|------|-------|------|
| 1 | 47902834 | Hernán | Choque Fernandez | 73259012 |

**INQUILINO**
| ID_Inquilino | CI | Nombre | Apellido | Telefono |
|------|------|------|-------|------|
| 1 | 56321208 | María | Flores | 73259012 |
| 2 | 45872136 | Juan | Mamani | 76543210 |
| 3 | 62145879 | Carlos | Quispe | 71234567 |

**CASA**
|ID_Casa | Dirección | Ciudad | Precio | Estado |
|------|------|------|-------|------|
| 1 | Av. Arce | La Paz | 2500 | Disponible |
| 2 | Calle Murillo | Cochabamba | 1800 | Alquilada |
| 3 | Av. Busch | Tarija | 2200 | Disponible |
| 4 | Ventura Mall | Santa Cruz | 1500 | Alquilada |

**Pago**
| ID_Contrato | Fecha | Monto |
|------|------|------|
| 1 | 22/07/2026 | 2500 |
| 2 | 13/11/2026 | 1800 |
| 3 | 10/05/2026 | 2200 |
