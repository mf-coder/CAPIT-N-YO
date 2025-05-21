<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Infografía: Navegando el Laberinto Laboral Argentino para "Capitán Yo"</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <!-- 
        Infographic Narrative Plan:
        1.  Title: "Navegando el Laberinto Laboral Argentino: Estrategias para la Operación Estacional 'Rental' de Capitán Yo".
        2.  Introduction/Hook: The challenge of seasonal operation without traditional employment in Argentina's high-risk legal environment.
        3.  Section 1: El Terreno Legal Argentino (The Argentinian Legal Terrain) - Key principles (Primacy of Reality, Public Labor Order), Presumption of Laborality, Impact of DNU 70/2023 (Attempted Change vs. Judicial Suspension).
        4.  Section 2: ¿Autónomo o Dependiente? La Delgada Línea Roja (Autonomous or Dependent? The Thin Red Line) - Indicia of Laborality (Radar Chart), Focus on Subordination.
        5.  Section 3: Figuras Contractuales Bajo la Lupa (Contractual Figures Under the Magnifying Glass) - Contract of Services, Contract of Work, Art. 96 DNU (Suspended).
        6.  Section 4: El Modelo "Rental": Riesgos y Consecuencias (The "Rental" Model: Risks and Consequences) - Flowchart of proposed structure and risks (Interposition, Joint Liability), Key Risks (Recalification, Fines), SWOT Analysis.
        7.  Section 5: Estrategias de Mitigación: Construyendo un Muro de Contención (Mitigation Strategies: Building a Containment Wall) - Pillars: Real Autonomy, Robust Contractual Design, Administrative Diligence, Constant Monitoring.
        8.  Section 6: Conclusión y Hoja de Ruta (Conclusion and Roadmap) - Reiterate high risk, key takeaways, call for continuous legal counsel.

        Visualization Choices:
        -   Intro: Large text "ALTO RIESGO", conceptual risk percentage. (HTML/Tailwind)
        -   Sec 1: Foundational pillars (HTML/Tailwind), Scale graphic for Presumption (HTML/CSS), Contrasting blocks for DNU impact (HTML/Tailwind).
        -   Sec 2: Radar Chart for Indicia of Laborality (Chart.js Canvas).
        -   Sec 3: Styled HTML cards for contractual figures (HTML/Tailwind).
        -   Sec 4: Flowchart using HTML/CSS divs for risk flow, SWOT grid (HTML/Tailwind), List with Unicode icons for key risks.
        -   Sec 5: Styled cards/columns with Unicode icons for mitigation pillars (HTML/Tailwind).
        -   Sec 6: Styled text callouts for takeaways (HTML/Tailwind).
        -   All visualizations will have contextual explanatory text.

        Palette Choice: "Sophisticated & Trustworthy"
        -   Background: #ECF0F1 (Light Gray)
        -   Card Background: #FFFFFF (White)
        -   Text (Dark): #2C3E50 (Dark Slate Blue)
        -   Primary Accent/Chart Color 1: #3498DB (Bright Blue)
        -   Secondary Accent/Chart Color 2: #2980B9 (Slightly Darker Blue)
        -   Warning/Risk Accent: #E74C3C (Red)
        -   Neutral/Supporting Accent: #95A5A6 (Medium Gray)

        NO SVG USED. NO MERMAID JS USED. All visuals are Chart.js (Canvas) or HTML/CSS with Tailwind.
    -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #ECF0F1;
            color: #2C3E50;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
        .section-title {
            color: #2C3E50;
            border-bottom: 2px solid #3498DB;
            padding-bottom: 0.5rem;
            margin-bottom: 1.5rem;
        }
        .card {
            background-color: #FFFFFF;
            border-radius: 0.5rem;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            padding: 1.5rem;
            margin-bottom: 1.5rem;
        }
        .stat-big {
            font-size: 3rem;
            font-weight: 700;
            color: #E74C3C;
        }
        .flowchart-node {
            background-color: #3498DB;
            color: white;
            padding: 0.75rem 1.25rem;
            border-radius: 0.375rem;
            text-align: center;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        .flowchart-arrow {
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: #2C3E50;
            margin: 0.5rem 0;
        }
        .swot-cell {
            border: 1px solid #BDC3C7;
            padding: 1rem;
            border-radius: 0.25rem;
        }
        .pillar-icon {
            font-size: 2.5rem;
            color: #3498DB;
            margin-bottom: 0.5rem;
        }
    </style>
</head>
<body class="antialiased">
    <header class="bg-[#2C3E50] text-white py-8 shadow-lg">
        <div class="container mx-auto px-6 text-center">
            <h1 class="text-3xl md:text-4xl font-bold mb-2">Navegando el Laberinto Laboral Argentino</h1>
            <p class="text-lg md:text-xl text-[#BDC3C7]">Estrategias para la Operación Estacional "Rental" de Capitán Yo</p>
        </div>
    </header>

    <main class="container mx-auto px-6 py-8">

        <section id="intro" class="mb-12 card text-center">
            <h2 class="text-2xl font-semibold section-title">El Desafío: Operar en Temporada Alta Evitando Riesgos</h2>
            <p class="text-lg mb-4">"Capitán Yo" busca operar su "Rental" de equipos de nieve de forma estacional. El objetivo es claro: máxima flexibilidad y eficiencia, minimizando los costos y complejidades de la contratación laboral tradicional. Sin embargo, el marco legal argentino presenta un terreno complejo y de alto riesgo para los esquemas de trabajo independiente.</p>
            <div class="stat-big">ALTO RIESGO</div>
            <p class="text-md text-[#95A5A6]">Potencial de reclasificación laboral sin una gestión legal y operativa impecable.</p>
            <p class="mt-4 text-sm">Este informe visualiza los hallazgos clave del análisis de viabilidad legal, ofreciendo una hoja de ruta para "Capitán Yo".</p>
        </section>

        <section id="terreno-legal" class="mb-12">
            <h2 class="text-2xl font-semibold section-title">1. El Terreno Legal Argentino: Principios y Realidades</h2>
            <p class="mb-6 text-lg">Comprender los cimientos del derecho laboral argentino es crucial. Dos principios rigen la interpretación de cualquier relación de trabajo:</p>
            <div class="grid md:grid-cols-2 gap-6 mb-8">
                <div class="card">
                    <h3 class="text-xl font-semibold text-[#3498DB] mb-2">📜 Principio de Primacía de la Realidad</h3>
                    <p>Lo que sucede en la práctica prevalece sobre lo que dicen los papeles. Un contrato "autónomo" no es suficiente si los hechos demuestran dependencia.</p>
                </div>
                <div class="card">
                    <h3 class="text-xl font-semibold text-[#3498DB] mb-2">🏛️ Orden Público Laboral</h3>
                    <p>Las leyes laborales son imperativas. Los derechos de los trabajadores no pueden ser renunciados ni disminuidos por acuerdos privados.</p>
                </div>
            </div>

            <div class="card mb-8">
                <h3 class="text-xl font-semibold mb-3">⚖️ Presunción de Laboralidad (Art. 23 LCT)</h3>
                <p class="mb-3">La ley presume que toda prestación de servicios es una relación laboral, salvo prueba en contrario. La carga de demostrar la autonomía recae en el empleador.</p>
                <div class="w-full bg-[#BDC3C7] rounded-full h-6 relative">
                    <div class="bg-[#3498DB] h-6 rounded-full text-xs text-white flex items-center justify-center" style="width: 75%;">Tiende a Relación Laboral</div>
                </div>
                <p class="text-sm mt-2 text-[#95A5A6]">Esta presunción es un obstáculo significativo para los esquemas de trabajo independiente.</p>
            </div>

            <div class="card">
                <h3 class="text-xl font-semibold mb-3">⚠️ Impacto del DNU 70/2023 y su Suspensión Judicial</h3>
                <p class="mb-4">El Decreto de Necesidad y Urgencia 70/2023 intentó introducir cambios para flexibilizar la contratación de autónomos (ej. modificación Art. 23 LCT, creación Art. 96 para independientes con colaboradores).</p>
                <div class="grid md:grid-cols-2 gap-4">
                    <div class="p-4 bg-yellow-100 border-l-4 border-yellow-500 text-yellow-700 rounded">
                        <h4 class="font-bold">Intento de Reforma (DNU 70/2023)</h4>
                        <p class="text-sm">Buscaba atenuar la presunción de laboralidad y validar esquemas de colaboración autónoma.</p>
                    </div>
                    <div class="p-4 bg-red-100 border-l-4 border-red-500 text-red-700 rounded">
                        <h4 class="font-bold">🚫 Suspensión Judicial</h4>
                        <p class="text-sm">Gran parte del capítulo laboral del DNU fue suspendido por la Justicia. Actualmente, estas reformas no son aplicables, rigiendo la normativa pre-DNU.</p>
                    </div>
                </div>
                <p class="mt-4 text-sm text-[#95A5A6]">Esta incertidumbre legal exige máxima cautela y basar las decisiones en el marco legal vigente y la jurisprudencia consolidada.</p>
            </div>
        </section>

        <section id="autonomo-dependiente" class="mb-12">
            <h2 class="text-2xl font-semibold section-title">2. ¿Autónomo o Dependiente? La Delgada Línea Roja</h2>
            <p class="mb-6 text-lg">La jurisprudencia utiliza la "teoría del haz indiciario" para determinar si existe una relación laboral encubierta. Estos son los factores clave que analizan los jueces:</p>
            <div class="card">
                <h3 class="text-xl font-semibold text-center mb-4">Indicios Clave de Laboralidad</h3>
                <div class="chart-container mx-auto">
                    <canvas id="indiciaRadarChart"></canvas>
                </div>
                <p class="mt-4 text-sm text-center text-[#95A5A6]">Un puntaje alto en múltiples indicios (especialmente subordinación) aumenta drásticamente el riesgo de recalificación.</p>
                <div class="mt-6 p-4 bg-blue-50 border-l-4 border-[#3498DB] text-[#2C3E50] rounded">
                    <h4 class="font-bold">🔎 Foco en la Subordinación:</h4>
                    <ul class="list-disc list-inside text-sm mt-2">
                        <li><strong>Jurídica:</strong> Recibir órdenes, cumplir horarios, estar sujeto a control y sanciones.</li>
                        <li><strong>Económica:</strong> Depender financieramente de un solo "cliente", no asumir riesgos del negocio.</li>
                        <li><strong>Técnica:</strong> Utilizar herramientas o métodos impuestos por la empresa.</li>
                    </ul>
                </div>
            </div>
        </section>

        <section id="figuras-contractuales" class="mb-12">
            <h2 class="text-2xl font-semibold section-title">3. Figuras Contractuales Bajo la Lupa</h2>
            <p class="mb-6 text-lg">La legislación argentina ofrece alternativas al contrato laboral tradicional, pero su validez depende de una autonomía real y demostrable.</p>
            <div class="grid md:grid-cols-1 lg:grid-cols-3 gap-6">
                <div class="card">
                    <h3 class="text-xl font-semibold text-[#3498DB] mb-2">📄 Contrato de Servicios (CCyCN)</h3>
                    <p class="text-sm mb-3">Un prestador se obliga a realizar un servicio a favor de un comitente, de forma independiente y mediante retribución.</p>
                    <h4 class="font-semibold text-sm mb-1">Claves para Validez:</h4>
                    <ul class="list-disc list-inside text-xs mb-2">
                        <li>Ausencia total de subordinación.</li>
                        <li>Asunción de riesgos por el prestador.</li>
                        <li>Provisión de herramientas propias.</li>
                        <li>No exclusividad (idealmente).</li>
                        <li>Retribución por servicio/resultado.</li>
                    </ul>
                    <p class="text-xs text-[#E74C3C]"><strong>Riesgo Principal:</strong> Fácil desnaturalización si hay indicios de dependencia.</p>
                </div>
                <div class="card">
                    <h3 class="text-xl font-semibold text-[#3498DB] mb-2">🛠️ Contrato de Obra (CCyCN)</h3>
                    <p class="text-sm mb-3">Un contratista se obliga a un resultado específico y determinado (obra material o intelectual), con independencia.</p>
                    <h4 class="font-semibold text-sm mb-1">Claves para Validez:</h4>
                    <ul class="list-disc list-inside text-xs mb-2">
                        <li>Resultado concreto y tangible.</li>
                        <li>Autonomía en la ejecución.</li>
                        <li>Asunción de riesgos de la obra.</li>
                        <li>Retribución por la obra finalizada.</li>
                    </ul>
                    <p class="text-xs text-[#E74C3C]"><strong>Riesgo Principal:</strong> Menos adecuado para servicios continuos como un "Rental", más para proyectos específicos.</p>
                </div>
                <div class="card border-2 border-dashed border-yellow-500 bg-yellow-50">
                    <h3 class="text-xl font-semibold text-yellow-600 mb-2">👥 Art. 96 DNU 70/2023 (Trab. Indep. con Colaboradores)</h3>
                    <p class="text-sm mb-3">Permitiría a un independiente tener hasta 5 colaboradores autónomos bajo un régimen especial.</p>
                     <div class="p-3 bg-red-100 border-l-4 border-red-500 text-red-700 rounded mb-2">
                        <h4 class="font-bold text-sm">🚨 ACTUALMENTE SUSPENDIDO 🚨</h4>
                    </div>
                    <h4 class="font-semibold text-sm mb-1">Potencial (si se validara y reglamentara):</h4>
                    <ul class="list-disc list-inside text-xs mb-2">
                        <li>Validación de colaboración autónoma.</li>
                        <li>Aportes unificados.</li>
                        <li>Ausencia de vínculo de dependencia.</li>
                    </ul>
                    <p class="text-xs text-[#E74C3C]"><strong>Estado Actual:</strong> No aplicable por suspensión judicial y falta de reglamentación. No se puede confiar en esta figura hoy.</p>
                </div>
            </div>
        </section>

        <section id="modelo-rental" class="mb-12">
            <h2 class="text-2xl font-semibold section-title">4. El Modelo "Rental": Riesgos y Consecuencias</h2>
            <p class="mb-6 text-lg">El esquema propuesto (Capitán Yo → Trabajador Independiente Principal → Colaboradores) es complejo y presenta múltiples puntos de riesgo.</p>
            
            <div class="card mb-8">
                <h3 class="text-xl font-semibold text-center mb-4">Flujo de Contratación Propuesto y Riesgos Clave</h3>
                <div class="flex flex-col items-center">
                    <div class="flowchart-node w-full md:w-1/2">Capitán Yo S.A.</div>
                    <div class="flowchart-arrow">⬇️</div>
                    <div class="text-xs text-[#E74C3C] mb-1 text-center">Contrato de Servicios (Riesgo de dependencia directa)</div>
                    <div class="flowchart-node w-full md:w-1/2">Trabajador Independiente Principal (Monotributista)</div>
                    <div class="flowchart-arrow">⬇️</div>
                     <div class="text-xs text-[#E74C3C] mb-1 text-center">Contratos de Servicios entre autónomos (Riesgo de dependencia del Principal o de Capitán Yo por interposición)</div>
                    <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-2 w-full justify-center">
                        <div class="flowchart-node text-sm">Colab. 1</div>
                        <div class="flowchart-node text-sm">Colab. 2</div>
                        <div class="flowchart-node text-sm">Colab. 3</div>
                        <div class="flowchart-node text-sm">Colab. 4</div>
                        <div class="flowchart-node text-sm">Colab. 5</div>
                    </div>
                </div>
                <div class="mt-6 p-4 bg-red-100 border-l-4 border-red-500 text-red-700 rounded">
                    <h4 class="font-bold">🚨 Zonas de Peligro:</h4>
                    <ul class="list-disc list-inside text-sm mt-2">
                        <li><strong>Interposición Ilícita (Art. 14 LCT):</strong> Si el Trabajador Independiente Principal es visto como un mero intermediario para encubrir la relación de los colaboradores con Capitán Yo.</li>
                        <li><strong>Responsabilidad Solidaria (Art. 29 y 30 LCT):</strong> Capitán Yo podría ser responsable por las obligaciones laborales de todos los involucrados si el "Rental" se considera actividad normal y específica propia, o si hay fraude.</li>
                    </ul>
                </div>
            </div>

            <div class="card mb-8">
                <h3 class="text-xl font-semibold mb-3">Análisis FODA del Modelo Propuesto para "Capitán Yo"</h3>
                <div class="grid md:grid-cols-2 gap-4">
                    <div class="swot-cell bg-green-50">
                        <h4 class="font-bold text-green-700">🟢 Fortalezas (Internas, Positivas)</h4>
                        <ul class="list-disc list-inside text-sm mt-1">
                            <li>Potencial flexibilidad operativa.</li>
                            <li>Posible reducción de costos directos de personal (si el esquema es válido).</li>
                            <li>Adaptabilidad a la estacionalidad del negocio.</li>
                        </ul>
                    </div>
                    <div class="swot-cell bg-red-50">
                        <h4 class="font-bold text-red-700">🔴 Debilidades (Internas, Negativas)</h4>
                        <ul class="list-disc list-inside text-sm mt-1">
                            <li>Alto riesgo de recalificación laboral.</li>
                            <li>Complejidad en la gestión y control de la autonomía real.</li>
                            <li>Necesidad de asesoramiento legal constante y costoso.</li>
                            <li>Vulnerabilidad a inspecciones y litigios.</li>
                        </ul>
                    </div>
                    <div class="swot-cell bg-blue-50">
                        <h4 class="font-bold text-blue-700">🔵 Oportunidades (Externas, Positivas)</h4>
                        <ul class="list-disc list-inside text-sm mt-1">
                            <li>Eventual validación y reglamentación del DNU 70/2023 (incierto).</li>
                            <li>Desarrollo de un modelo de negocio innovador (si se logra legalidad).</li>
                            <li>Posibilidad de atraer talento que prefiera esquemas autónomos (con cautela).</li>
                        </ul>
                    </div>
                    <div class="swot-cell bg-yellow-50">
                        <h4 class="font-bold text-yellow-700">🟡 Amenazas (Externas, Negativas)</h4>
                        <ul class="list-disc list-inside text-sm mt-1">
                            <li>Interpretación judicial restrictiva y protectoria.</li>
                            <li>Cambios legislativos desfavorables.</li>
                            <li>Accionar de sindicatos y autoridades de fiscalización (Ministerio, AFIP).</li>
                            <li>Precedentes judiciales adversos.</li>
                        </ul>
                    </div>
                </div>
            </div>
             <div class="card">
                <h3 class="text-xl font-semibold text-[#E74C3C] mb-3">Principales Consecuencias de una Recalificación:</h3>
                <ul class="space-y-2">
                    <li class="flex items-start"><span class="text-red-500 mr-2">⚠️</span> Pago retroactivo de salarios, aguinaldos, vacaciones no gozadas.</li>
                    <li class="flex items-start"><span class="text-red-500 mr-2">⚠️</span> Multas por falta de registración (Leyes 24.013, 25.323 - derogaciones del DNU 70/2023 suspendidas).</li>
                    <li class="flex items-start"><span class="text-red-500 mr-2">⚠️</span> Deudas por aportes y contribuciones a la seguridad social (jubilación, obra social, ART) con intereses.</li>
                    <li class="flex items-start"><span class="text-red-500 mr-2">⚠️</span> Indemnizaciones por despido (potencialmente agravadas).</li>
                    <li class="flex items-start"><span class="text-red-500 mr-2">⚠️</span> Costas judiciales y honorarios profesionales.</li>
                </ul>
            </div>
        </section>

        <section id="estrategias-mitigacion" class="mb-12">
            <h2 class="text-2xl font-semibold section-title">5. Estrategias de Mitigación: Construyendo un Muro de Contención</h2>
            <p class="mb-6 text-lg">Minimizar los riesgos exige un enfoque integral que combine diseño contractual, implementación operativa y diligencia administrativa.</p>
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
                <div class="card text-center">
                    <div class="pillar-icon">🤝</div>
                    <h3 class="text-xl font-semibold text-[#3498DB] mb-2">Autonomía Real y Demostrable</h3>
                    <p class="text-sm">La práctica diaria debe reflejar independencia. El contratista debe gestionar sus tiempos, métodos y recursos sin subordinación a Capitán Yo.</p>
                </div>
                <div class="card text-center">
                    <div class="pillar-icon">📜</div>
                    <h3 class="text-xl font-semibold text-[#3498DB] mb-2">Diseño Contractual Robusto</h3>
                    <p class="text-sm">Contratos civiles/comerciales claros, que enfaticen la autonomía, no exclusividad, retribución por resultado y asunción de riesgos por el contratista.</p>
                </div>
                <div class="card text-center">
                    <div class="pillar-icon">📊</div>
                    <h3 class="text-xl font-semibold text-[#3498DB] mb-2">Diligencia Administrativa</h3>
                    <p class="text-sm">Facturación adecuada (Monotributo/Resp. Inscripto), pagos bancarizados, verificación de cumplimiento fiscal y de seguridad social del contratista.</p>
                </div>
                <div class="card text-center">
                    <div class="pillar-icon">🔍</div>
                    <h3 class="text-xl font-semibold text-[#3498DB] mb-2">Monitoreo Legal Constante</h3>
                    <p class="text-sm">Seguimiento de cambios normativos, jurisprudencia y evolución del DNU 70/2023. Asesoramiento legal continuo.</p>
                </div>
            </div>
             <div class="mt-6 card bg-blue-50 border-t-4 border-[#3498DB]">
                <h4 class="text-lg font-semibold text-[#2C3E50] mb-2">Checklist Preventivo para Capitán Yo:</h4>
                <ul class="list-disc list-inside text-sm space-y-1">
                    <li>¿El contrato con el independiente principal es de servicios/obra y no simula laboralidad?</li>
                    <li>¿El independiente principal provee sus propias herramientas y asume riesgos?</li>
                    <li>¿El independiente principal tiene libertad para organizar su trabajo y el de sus colaboradores?</li>
                    <li>¿Se evita la exclusividad de facto? ¿Puede prestar servicios a otros?</li>
                    <li>¿La remuneración es por proyecto/servicio y no un salario fijo mensual?</li>
                    <li>¿Capitán Yo NO da órdenes directas a los colaboradores del independiente?</li>
                    <li>¿Se documentan todas las transacciones (facturas, pagos bancarios)?</li>
                    <li>¿Se capacita al personal de Capitán Yo sobre cómo interactuar con contratistas autónomos?</li>
                </ul>
            </div>
        </section>

        <section id="conclusion" class="mb-12">
            <h2 class="text-2xl font-semibold section-title">6. Conclusión y Hoja de Ruta para "Capitán Yo"</h2>
            <div class="card">
                <p class="text-lg mb-4">Operar el "Rental" bajo un esquema de trabajo independiente en Argentina es **viable conceptualmente, pero extremadamente riesgoso si no se implementa con máxima diligencia y coherencia.** La suspensión del capítulo laboral del DNU 70/2023 refuerza la necesidad de cautela.</p>
                <div class="grid md:grid-cols-2 gap-6 mb-6">
                    <div class="p-4 bg-[#ECF0F1] rounded-lg shadow">
                        <h4 class="font-bold text-[#2C3E50] text-lg mb-2">💡 Mensajes Clave:</h4>
                        <ul class="list-none space-y-2">
                            <li class="flex items-center"><span class="text-[#3498DB] text-xl mr-2">»</span> La Realidad Manda: Los hechos prevalecen sobre los papeles.</li>
                            <li class="flex items-center"><span class="text-[#3498DB] text-xl mr-2">»</span> Autonomía Genuina: No solo declarada, sino vivida y demostrable.</li>
                            <li class="flex items-center"><span class="text-[#3498DB] text-xl mr-2">»</span> Documentación Rigurosa: Contratos, facturas, pagos. Todo en regla.</li>
                            <li class="flex items-center"><span class="text-[#E74C3C] text-xl mr-2">»</span> Riesgo Latente: La recalificación siempre es una posibilidad.</li>
                        </ul>
                    </div>
                     <div class="p-4 bg-[#3498DB] text-white rounded-lg shadow">
                        <h4 class="font-bold text-lg mb-2">🗺️ Hoja de Ruta Recomendada:</h4>
                        <ol class="list-decimal list-inside space-y-2 text-sm">
                            <li><strong>Asesoramiento Legal Especializado y Continuo:</strong> Indispensable antes, durante y después de la implementación.</li>
                            <li><strong>Diseño Detallado del Modelo Operativo:</strong> Definiendo claramente roles, responsabilidades y límites para asegurar la autonomía.</li>
                            <li><strong>Implementación Gradual y Controlada:</strong> Quizás iniciar con un piloto y evaluar.</li>
                            <li><strong>Auditorías Internas Periódicas:</strong> Para verificar el cumplimiento y corregir desvíos.</li>
                            <li><strong>Evaluación Constante Riesgo vs. Beneficio:</strong> Estar preparado para ajustar o incluso reconsiderar el modelo si los riesgos aumentan.</li>
                        </ol>
                    </div>
                </div>
                <p class="text-center font-semibold text-lg text-[#2C3E50]">La prudencia y el cumplimiento estricto son los mejores aliados de "Capitán Yo" en esta travesía.</p>
            </div>
        </section>
    </main>

    <footer class="bg-[#2C3E50] text-white text-center py-6 mt-12">
        <p class="text-sm">&copy; 2024 Análisis Legal para Capitán Yo. Infografía generada con fines informativos.</p>
        <p class="text-xs text-[#95A5A6]">La información aquí presentada no constituye asesoramiento legal definitivo y debe ser complementada con consulta profesional.</p>
    </footer>

    <script>
        function processLabel(label, maxLength = 16) {
            if (label.length <= maxLength) {
                return label;
            }
            const words = label.split(' ');
            const lines = [];
            let currentLine = '';
            for (const word of words) {
                if ((currentLine + word).length > maxLength && currentLine.length > 0) {
                    lines.push(currentLine.trim());
                    currentLine = word + ' ';
                } else {
                    currentLine += word + ' ';
                }
            }
            if (currentLine.trim().length > 0) {
                lines.push(currentLine.trim());
            }
            return lines;
        }

        const tooltipTitleCallback = function(tooltipItems) {
            const item = tooltipItems[0];
            let label = item.chart.data.labels[item.dataIndex];
            if (Array.isArray(label)) {
              return label.join(' ');
            } else {
              return label;
            }
        };

        const indiciaData = {
            labels: [
                processLabel('Subordinación Jurídica'), 
                processLabel('Subordinación Económica'), 
                processLabel('Subordinación Técnica'), 
                processLabel('Ajenidad en Riesgos/Frutos'), 
                processLabel('Exclusividad'), 
                processLabel('Habitualidad y Continuidad'), 
                processLabel('Cumplimiento de Horarios'), 
                processLabel('Integración Organización Ajena')
            ],
            datasets: [{
                label: 'Nivel de Riesgo de Laboralidad (Conceptual)',
                data: [8, 7, 6, 7, 5, 6, 7, 6], // Conceptual data: higher means more indicative of labor relationship
                fill: true,
                backgroundColor: 'rgba(52, 152, 219, 0.2)', // #3498DB with alpha
                borderColor: '#3498DB',
                pointBackgroundColor: '#3498DB',
                pointBorderColor: '#fff',
                pointHoverBackgroundColor: '#fff',
                pointHoverBorderColor: '#3498DB'
            }]
        };

        const indiciaConfig = {
            type: 'radar',
            data: indiciaData,
            options: {
                responsive: true,
                maintainAspectRatio: false,
                elements: {
                    line: {
                        borderWidth: 3
                    }
                },
                scales: {
                    r: {
                        angleLines: {
                            display: true,
                            color: '#BDC3C7'
                        },
                        suggestedMin: 0,
                        suggestedMax: 10,
                        grid: {
                            color: '#ECF0F1' 
                        },
                        pointLabels: {
                            font: {
                                size: 10
                            },
                            color: '#2C3E50'
                        },
                        ticks: {
                           display: false, // Hide the radial numbers for cleaner look
                           stepSize: 2
                        }
                    }
                },
                plugins: {
                    legend: {
                        position: 'top',
                        labels: {
                             color: '#2C3E50'
                        }
                    },
                    tooltip: {
                        callbacks: {
                            title: tooltipTitleCallback
                        }
                    }
                }
            }
        };

        window.onload = function() {
            const ctxRadar = document.getElementById('indiciaRadarChart');
            if (ctxRadar) {
                new Chart(ctxRadar, indiciaConfig);
            }
        };
    </script>

</body>
</html>
