# PracticoU1
Entrevista a base de datos
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistema de Gestión de Alquiler de Casas</title>

    <link rel="stylesheet" href="estilo.css">
</head>

<body>

    <header>
        <h1>UNIT 1 - SPANISH INTERVIEW AND UML DIAGRAM FOR THE STARTING OF PROJECT</h1>
    </header>

    <main>

        <!-- TÍTULO DEL PROYECTO -->
        <section class="proyecto">

            <h2>🏠 Proyecto de Curso: Sistema de Gestión de Alquiler de Casas</h2>

            <p>
                Este proyecto surge como caso de estudio para la materia
                <strong>Bases de Datos 1</strong> de la carrera de
                <strong>Ingeniería Informática</strong> en la
                <strong>Universidad Autónoma Gabriel René Moreno (UAGRM)</strong>.
                El objetivo principal es realizar el diseño conceptual, lógico y físico
                de una base de datos que permita administrar la información de casas
                en alquiler, clientes y contratos.
            </p>

        </section>


        <!-- ENTREVISTA -->
        <section>

            <h2>🗣️ Transcripción de la Entrevista – Dueño de Alquiler de Casas</h2>

            <div class="datos">
                <p>
                    <strong>Entrevistador:</strong>
                    Estudiante de Ingeniería Informática (UAGRM)
                </p>

                <p>
                    <strong>Entrevistado:</strong>
                    Sr. Carlos Mendoza (Propietario de casas en alquiler)
                </p>
            </div>


            <div class="contenido">

                <!-- PREGUNTAS -->
                <div class="entrevista">

                    <h2>💬 Entrevista</h2>

                    <div class="pregunta">
                        <strong>P:</strong>
                        ¿Desde hace cuánto tiempo se dedica al alquiler de casas?
                    </div>

                    <div class="respuesta">
                        <strong>R:</strong>
                        Aproximadamente desde hace 8 años. Comencé con una casa
                        y actualmente tengo 5 propiedades que alquilo.
                    </div>


                    <div class="pregunta">
                        <strong>P:</strong>
                        ¿Qué tipo de casas ofrece en alquiler?
                    </div>

                    <div class="respuesta">
                        <strong>R:</strong>
                        Tengo casas de 2 y 3 dormitorios, algunas amobladas y
                        otras sin amoblar. También cuento con garajes y algunas
                        propiedades tienen patio.
                    </div>


                    <div class="pregunta">
                        <strong>P:</strong>
                        ¿Cómo es el proceso actual para alquilar una casa?
                    </div>

                    <div class="respuesta">
                        <strong>R:</strong>
                        Los interesados me contactan por teléfono o redes sociales.
                        Me preguntan por la disponibilidad y el precio. Luego hacemos
                        una visita, revisamos los documentos y finalmente firmamos
                        un contrato.
                    </div>


                    <div class="pregunta">
                        <strong>P:</strong>
                        ¿Qué información considera importante registrar?
                    </div>

                    <div class="respuesta">
                        <strong>R:</strong>
                        El nombre del inquilino, sus datos de contacto, la casa que
                        alquila, el monto del alquiler, la duración del contrato y
                        el estado del inmueble al momento de la entrega.
                    </div>


                    <div class="pregunta">
                        <strong>P:</strong>
                        ¿Qué dificultades ha tenido en este proceso?
                    </div>

                    <div class="respuesta">
                        <strong>R:</strong>
                        A veces es difícil llevar el control de los contratos y
                        los pagos. También existen clientes que no cumplen con
                        las fechas de pago o que pueden causar daños a la propiedad.
                    </div>


                    <div class="pregunta">
                        <strong>P:</strong>
                        ¿Le gustaría tener un sistema que le ayude a gestionar
                        estos procesos?
                    </div>

                    <div class="respuesta">
                        <strong>R:</strong>
                        Sí, sería muy útil. Me permitiría llevar un mejor control
                        de los inquilinos, los contratos y los pagos, y así evitar
                        problemas.
                    </div>

                </div>


                <!-- UML -->
                <div class="uml">

                    <h2>📊 Diagrama UML - Casos de Uso</h2>

                    <div class="diagrama">

                        <div class="actor propietario">
                            👤
                            <span>Propietario</span>
                        </div>


                        <div class="sistema">

                            <h3>Sistema de Gestión<br>de Alquiler de Casas</h3>

                            <div class="caso">
                                Registrar casa
                            </div>

                            <div class="caso">
                                Gestionar inquilinos
                            </div>

                            <div class="caso">
                                Crear contrato
                            </div>

                            <div class="caso">
                                Registrar pagos
                            </div>

                            <div class="caso">
                                Consultar información
                            </div>

                            <div class="caso">
                                Generar reportes
                            </div>

                        </div>


                        <div class="actor inquilino">
                            👤
                            <span>Inquilino</span>
                        </div>

                    </div>


                    <!-- CONCLUSIÓN -->
                    <div class="conclusion">

                        <h2>📋 Conclusión</h2>

                        <p>
                            La entrevista permitió identificar los principales
                            requisitos del sistema, como el registro de casas,
                            inquilinos, contratos y pagos. Con esta información
                            se podrá diseñar una base de datos que facilite la
                            administración de los alquileres y permita llevar
                            un mejor control de las propiedades.
                        </p>

                    </div>

                </div>

            </div>

        </section>

    </main>


    <footer>
        <p>Proyecto de Bases de Datos 1 - Ingeniería Informática - UAGRM</p>
    </footer>

    <script src="script.js"></script>

</body>
</html>
