
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

**CASA**
* id_casa
* habitaciones
* baño
* estado_de_casa
* numero_de_pisos
* garaje
* dirección
* ciudad
* zona
* precio_mensual
 
**INQUILINO**
* id_inquilino
* CI
* Nombre
* Apellido
* Teléfono
* correo

**CONTRATO**
* id_contrato
* id_casa
* id_inquilino
* Fecha_inicio
* Fecha_fin
* precio_acordado
* plazo_pago
* estado
* forma_pago
* observaciones

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

| id_casa → direccion |            
|----------|
| ciudad | 
| zona | 
| habitaciones | 
| banos | 
|numero_pisos |
| garaje | 
| precio_mensual |
| estado_casa | 

| id_inquilino → ci |
|------------|
| nombre | 
| apellido |
| telefono |
| correo |

| id_contrato → id_casa |
|------------|
| id_inquilino | 
| fecha_inicio | 
| fecha_fin | 
| precio_acordado | 
| forma_pago | 
| estado_contrato |

| id_pago → id_contrato |
|-----------|
| numero_pago | 
| fecha_pago |
| monto | 
| metodo_pago |
| estado_pago |

## **Primer Forma Normal (1NF)**

**Tabla inquilino**
| id_inquilino (PK) | nombre | apellido | telefono | correo |
| ------- | ------- | ------ | ------ | ----- |
| 1 | María | Flores | 73259012 | maria.f@email.com |
| 2 | Juan | Mamani | 76543210 | juan.m@email.com |
| 3 | Carlos | Quispe | 71234567 | carlos.q@email.com |

**Tabla casa**
| id_casa (PK) | precio_mensual | estado_casa |
| ------- | ------- | ------ |
| 1 | 3500 | Alquilada |
| 2 | 2200 | Alquilada |
| 3 | 4200 | Disponible |

**Tabla contrato**
| id_contrato (PK) | id_inquilino (FK) | id_casa (FK) | fecha_inicio | fecha_fin | precio_acordado | estado_contrato |
| ------- | ------- | ------- | -------- | ------- | ------- | --------- |
| 1 | 1 | 1 | 10/05/2026 | 10/05/2027 | 3500 | Vigente |
| 2 | 2 | 2 | 01/08/2026 | 01/02/2027 | 2200 | Vigente |

**Tabla pago**
| id_pago (PK) | id_contrato (FK) | fecha_pago | monto | estado_pago |
| ------- | ------- | ------- | ------- | -------- |
| 1 | 1 | 10/05/2026 | 3500 | Pagado |
| 2 | 1 | 09/06/2026 | 3500 | Pagado |
| 3 | 2 | 01/08/2026 | 2200 | Pagado |

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
