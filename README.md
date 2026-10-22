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

**Facilitar la administración** de la informacion mediante un sistema que permita realizar consultas y actualizar 
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

# Normalización y Dependencias Funcionales

1. 

| Entidad | Clave |
|------|---------------|
| inquilino | id_inquilino |
| Casa | id_casa |
| Contrato | id_contrato |
| Pago | id_pago |

## **Primer Forma Normal (1NF)**

**Tabla inquilino**
| id_inquilino | CI | Nombre | Apellido | Telefono |
|------|------|------|-------|------|
| 1 | 56321208 | María | Flores | 73259012 |
| 2 | 45872136 | Juan | Mamani | 76543210 |
| 3 | 62145879 | Carlos | Quispe | 71234567 |
| 4 | 78945612 | Pedro | Choque | 70123456 |

**Tabla alquiler**
| id_alquiler (PK) | id_cliente (FK) | id_casa | 
|------|------|------|
| 1 | 1 | 1 |
| 2 | 1 | 2 | 
| 3 | 2 | 3 | 

**Tabla contrato**
| ID_Contrato | ID_Inquilino | ID_Casa | Fecha_Inicio | Fecha_Final |
|------|------|------|------|------|
| 1 | 8 | 1 | 10/05/2024 | 23/11/2025 |
| 2 | 5 | 2 | 23 /10/2022 | 11/03/ 2023 |
| 3 | 7 | 3 | 08/11/2021 | 05/12/2026 |

**Tabla pago**
|ID_Pago | ID_Contrato | Fecha | Monto |
|------|------|------|------|
| 1 | 3 | 22/07/2026 | 2500 |
| 2 | 8 | 13/11/2026 | 3800 |
| 3 | 6 | 10/05/2026 | 2200 |

## **Segunda Forma Normal (2NF)**

**Tabla inquilino**
| id_inquilino (PK) | Nombre |
|------|------|
| 3 | Carlos |
| 1 | María | 

**Tabla casa**
|id_casa (PK) | dirección |
|------|------|
| 10 | Calle Marketin |
| 11 | Calle B |

**Tabla contrato**
| id_contrato (FK) | id_inquilino (PK) | id_casa (PK) | fecha_inicio |
|------|------|------|-------|
| 1 | 1 | 10 | 01/12/2022 |
| 2 | 2 | 11 | 10/11/2021 |

**Tabla pago**
| id_pago (PK) | id_contrato | Monto |
|------|------|------|
| 1 | 3 | 3800 |
| 1 | 4 | 2500 |
| 3 | 1 | 3000 |

## Tercera Forma Normal (3NF)
**Tabla inquilino**
| id_inquilino (PK) | Nombre |
|------|------|
| 1 | | Carlos |
| 2 | María |

**Tabla casa**
| id_casa (PK) | dirección |
|------|-------|
| 1 | Calle Marketing |
| 3 | Calle B |

**tabla contrato**
| id_contrato (FK) | id_cliente (PK) | id_casa (PK) | Fecha_Inicio | 
|------|------|------|------|
| 1 | 3 | 4 | 23/10/2022 | 
| 3 | 5 | 8 | 08/11/2021 | 

**Tabla pago**
| id_pago (PK) | id_contrato (PK) | fecha_pago | Monto | 
|------|------|------|------|
| 2 | 8 | 13/11/2026 | 3800 |
| 7 | 5 | 10/09/2024 | 3000 |
