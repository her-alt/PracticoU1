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

**Suposiciones:**

* El inquilino se identifica por su CI.
* Cada casa tiene una dirección única.
* Un contrato pertenece a un solo inquilino y una sola casa.
* Un contrato puede tener muchos pagos.

---

# Entidades y atributos

**INQUILINO**
* id_inquilino(PK)
* CI
* Nombre
* Apellido
* Teléfono
 
**CASA**
* id_casa(PK)
* Dirección
* Zona
* Habitaciones
* Estado

**CONTRATO**
* id_contrato (PK)
* Fecha_inicio
* Fecha_fin
* Monto_mensual

**PAGO**
* id_pago (PK)
* Fecha_pago
* Monto
* Método

**Cardinalidades**
INQUILINO 1 ─ N CONTRATO
CASA 1 ─ N CONTRATO
CONTRATO 1 ─ N PAGO

# ESQUEMA SQL

entity INQUILINO {
  *id_inquilino : INT
  ci : VARCHAR
  nombre : VARCHAR
  apellido : VARCHAR
  telefono : VARCHAR
}

entity CASA {
  *id_casa : INT
  dirrecion: VARCHAR 
  zona : VARCHAR
  habitaciones : INT
  estado : VARCHAR
}

entity CONTRATO {
  *id_contrato : INT
  fecha_inicio : DATE
  fecha_fin : DATE
  monto_mensual : DECIMAL
}

entity PAGO {
  *id_pago : INT
  fecha_pago : DATE
  monto : DECIMAL
  metodo : VARCHAR
}

INQUILINO ||--o{ CONTRATO
CASA ||--o{ CONTRATO
CONTRATO ||--o{ PAGO
