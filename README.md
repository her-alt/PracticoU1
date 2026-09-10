UNIDAD 1 - ENTREVISTA EN ESPAÑOL Y DIAGRAMA UML PARA EL INICIO DEL PROYECTO
==============================================

# Proyecto de Curso: Sistema de Gestión de Alquiler de Casas "Casa en Renta"

Este proyecto surge como caso de estudio para la materia **Base de Datos 1** de la carrera de *Ingeniería Informática* en la 
**Universidad Autónoma Gabriel Rene Moreno (UAGRM)**. El objetivo principal es realizar el diseño conceptual, lógica y fisica de un
Base de Datos que resuelva los problemas de gestión, control y registro de la información de alquiler de casas, de un propietario
o empresa de alquiler de viviendas.

## 📋 Transcripción de la Entrevista del Dueño de Alquiler de Casas

*   **Entrevistador:** Estudiante de Ingeniería Informática (UAGRM)
*   **Entrevistado:** Hernan Fernandez/Dueño de la casa en alquiler

---

## 🏠 Sistema de Gestión de Alquiler de Casas — "Casas en Renta"
**Narración del cliente:**  
> "Soy Hernan Fernandez Necesito llevar un registro de los lugares, de las personas que las alquilan y de los contratos
> Quiero registrar los datos de cada casa, como su dirección, zona, número de habitaciones, precio mensual y estado.
> También necesito saber quién está alquilando cada casa, desde qué fecha hasta qué fecha y si realizó el pago correspondiente. Además,
> quiero poder consultar qué casas están disponibles y cuáles están alquiladas”

**Suposiciones:**

* Se identifica a cada inquilino de manera única mediante su número de teléfono o documento de identidad.
* Una persona puede alquilar una casa por un determinado período de tiempo. Una misma persona puede realizar varios alquileres en diferentes fechas, mientras que cada casa puede ser alquilada por diferentes personas a lo largo del tiempo.
* Cada casa tiene una dirección, zona, número de habitaciones, precio mensual y un estado que indica si está disponible o alquilada.
* Cada contrato de alquiler corresponde a una sola casa y a un solo inquilino, registrando la fecha de inicio, fecha de finalización y el monto acordado.
* Los pagos realizados por el inquilino se registran indicando la fecha, el monto y el método de pago utilizado.

---

## 📐 Diseño Conceptual (UML)

A continuación se presenta el diagrama de clases generado en **StarUML** que modela los requerimientos descritos en la entrevista:
