<script>
  import { goto } from '$app/navigation';
  import Carousel from '../components/Carousel.svelte';

  function gotoSectionDishes() {
    goto('/platillos'); 
  }

  const Headquarters = [
    {
      img: '/images/restaurante1.jpg',
      title: 'Sucursal principal',
      description: 'Visitanos en la carrera 12 #34-56, Pasto.'
    },
    {
      img: '/images/restaurante2.jpg',
      title: 'Segunda sucursal en el centro',
      description: 'Disfruta de nuestra ubicación en la calle 45 #67-89, Pasto.'
    },
    {
      img: '/images/restaurante3.jpg',
      title: 'Nueva sucursal en el norte',
      description: 'Encuéntranos en la avenida 10 #11-12, Pasto.'
    }
  ];
</script>

<section class="hero text-center p-5 bg-dark text-white">
  <h1 class="display-4">Bienvenid@ a Sara's Restaurant</h1>
  <p class="lead">Tu restaurante favorito, sigue abajo para obtener más información</p>
  <button class="btn btn-primary mt-3" on:click={gotoSectionDishes}>
    Nuestros mejores platos
  </button>
</section>

<section class="features container py-5">
  <h2 class="text-center mb-4">¿Qué puedes encontrar en nuestros restaurantes?</h2>
  <div class="row text-center">
    <div class="col-md-4">
      <i class="bi bi-controller fs-1 text-primary"></i>
      <h4 class="mt-2">Platillos</h4>
      <p>Descubre y disfruta nuevos sabores con nuestros platos recientes</p>
    </div>
    <div class="col-md-4">
      <i class="bi bi-chat-dots fs-1 text-success"></i>
      <h4 class="mt-2">Experiencia</h4>
      <p>Disfruta con tu mejor compañía de nuestros increibles restaurantes</p>
    </div>
    <div class="col-md-4">
      <i class="bi bi-lightning fs-1 text-warning"></i>
      <h4 class="mt-2">Novedades</h4>
      <p>Mantente al tanto de los eventos, lanzamientos y torneos del mundo gaming.</p>
    </div>
  </div>
</section>

<section class="container my-5">
  <h2 class="text-center mb-4">Nuestras sucursales</h2>
  <Carousel items={Headquarters} />
</section>

