<script>
    import { goto } from '$app/navigation';
    import { user } from '../../stores/auth.js';
    function cerrarSesion() {
        user.set({
        name: '',
        email: '',
        loged: false
      });
      goto('/');
    }
</script>
<div class="max-w-md max-h-full  mx-auto mt-20 p-6 bg-white rounded-lg shadow-md">
  <h1 class="text-2xl font-bold mb-4">Cerrar sesión</h1>
  <p class="mb-4">¿Estás seguro de que deseas cerrar sesión?</p>
  <button class="btn btn-danger" on:click={cerrarSesion}>Cerrar sesión</button>
</div>