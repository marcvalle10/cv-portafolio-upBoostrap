Equipo: Vallejo Leyva Marcos & Casas Gastelum Ana Cecilia

ACTIVIDAD 10 - MEJORAS CV CON BOOTSTRAP

Grid responsive

Qué es: El sistema de rejilla de Bootstrap (12 columnas) que ajusta el layout según el ancho de pantalla con clases como .row y .col-*.
Por qué: Permite diseñar una página que se vea bien en móviles, tablets y escritorio sin CSS extra.
Cómo se aplicó: Secciones como Sobre mí, Habilidades y Proyectos usan row + col-12 col-lg-* para cambiar de 1 a 2 columnas en pantallas grandes.

<div class="row g-4">
  <div class="col-12 col-lg-8">...</div>
  <div class="col-12 col-lg-4">...</div>
</div>

Componente nuevo (modal, carousel, tooltip)

Qué es: Elementos interactivos listos para usar de Bootstrap.
Por qué: Añaden funcionalidad y mejoran la experiencia sin re-crear componentes desde cero.
Cómo se aplicó:

Modal de contacto, activado desde el botón “Contáctame”.

<button class="btn btn-outline-light" data-bs-toggle="modal" data-bs-target="#contactoModal">
  Contáctame
</button>
<div class="modal fade" id="contactoModal" tabindex="-1" aria-labelledby="contactoModalLabel">
  <div class="modal-dialog"><div class="modal-content">...</div></div>
</div>


Carousel en Proyectos (INOXSON y Programa Delfín) para navegar capturas.
<img width="1722" height="653" alt="image" src="https://github.com/user-attachments/assets/b366c037-6192-4035-99ab-4dac91f65135" />



Tooltip en badges de habilidades/idiomas (p.ej., nivel de inglés).

<span class="badge rounded-pill text-bg-secondary" data-bs-toggle="tooltip" title="Marco Europeo">B1</span>
<script>
  [...document.querySelectorAll('[data-bs-toggle="tooltip"]')]
    .forEach(el => new bootstrap.Tooltip(el));
</script>

Personalización de colores (sin defaults)

Qué es: Sobrescribir los colores del tema usando variables CSS de Bootstrap (--bs-*).
Por qué: Da identidad visual y evita usar los colores por defecto.
Cómo se aplicó: En tu hoja styles.css redefiniste la paleta.

:root{
  --bs-primary:#2c7a7b; /* teal oscuro */
  --bs-success:#2f855a;
  --bs-info:#0ea5e9;
  --bs-body-bg:#0f0f10;
  --bs-body-color:#e9e9e9;
}
.bg-gradient-gray{
  background:linear-gradient(135deg,rgba(0,0,0,.85),rgba(20,20,20,.85)),url('./img/hero.jpg');
  background-size:cover; background-position:center;
}

Detalle de accesibilidad (aria-label, contraste, focus)

Qué es: Buenas prácticas para que todas las personas puedan usar el sitio (lectores de pantalla, teclado, etc.).
Por qué: Mejora usabilidad, cumplimiento y experiencia.
Cómo se aplicó:

aria-label en navbar, botones del carrusel y enlaces externos.

Foco visible con :focus-visible para navegación por teclado.

Contraste reforzado en el hero (fondo oscuro + texto claro).

<nav class="navbar ..." aria-label="Navegación principal">...</nav>
<button class="carousel-control-next" aria-label="Siguiente">...</button>

:focus-visible{ outline:2px solid #fff; outline-offset:2px; }

Badges o etiquetas (habilidades/idiomas/certificaciones)

Qué es: Pequeñas etiquetas visuales para destacar tags o niveles.
Por qué: Escaneabilidad: el lector identifica rápido tecnologías, niveles y horas.
Cómo se aplicó: Badges redondeadas en Habilidades, Idiomas y horas en Certificaciones (con list-group).

<span class="badge rounded-pill text-bg-primary">JavaScript</span>
<li class="list-group-item d-flex justify-content-between align-items-center">
  Elements of AI <span class="badge rounded-pill text-bg-secondary">50 h</span>
</li>

Espaciados y sombras (utilidades m-*, p-*, shadow)

Qué es: Clases utilitarias que aplican márgenes, paddings y sombras sin CSS adicional.
Por qué: Prototipado rápido y consistencia visual.
Cómo se aplicó: Tarjetas con p-4, secciones con py-5, y relieve con shadow-sm/shadow.

<section id="skills" class="py-5 bg-body-tertiary border-top">
  <div class="container">
    <div class="p-4 rounded-4 bg-white shadow-sm h-100">...</div>
  </div>
</section>

Resultados visibles en CV

El layout cambia de una a dos columnas según el tamaño de pantalla (grid responsive).

El modal facilita el contacto, el carrusel enseña capturas y tooltips añaden contexto.

La paleta propia (teal/grises) unifica el estilo.

Accesibilidad: navegación clara, foco visible y labels para lectores de pantalla.

Badges resumen habilidades, niveles e horas de cursos de forma rápida.

Utilidades de espaciado/sombras dan jerarquía y mejor legibilidad sin CSS extra.
