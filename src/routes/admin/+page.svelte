<script>
    import { onMount } from 'svelte';   
    import { goto } from '$app/navigation';
	import { user } from '../../stores/auth';

    let currentUser = {
        name: '',
        email: '',
        loged: false
    };
    onMount(() => {
        user.subscribe(value => {
            currentUser = value;
            if (!currentUser) goto('/login');
        });
    });
    
</script>

<div class="admin-section">
  <div class="text-center mb-4">
    <h2>Bienvenida, {currentUser.name} </h2>
    <p class="text-muted">Panel de administración del restaurante</p>
  </div>

  <div class="card shadow-sm mb-4">
    <div class="card-body">
      <h5 class="card-title">Gestión de pedidos</h5>
      <p class="card-text">Aquí podrás revisar, editar y actualizar los pedidos de los clientes.</p>
      <div class="feature-placeholder">
        Funcionalidad en desarrollo...
      </div>
    </div>
  </div>

  <div class="card shadow-sm mb-4">
    <div class="card-body">
      <h5 class="card-title">Menú del día</h5>
      <p class="card-text">Agrega o edita los platos disponibles diariamente.</p>
      <div class="feature-placeholder">
         Muy pronto podrás gestionar tu menú desde aquí...
      </div>
    </div>
  </div>

  <div class="alert alert-info text-center mt-4">
     Nuevas funciones se agregarán próximamente. ¡Mantente atenta, Sara!
  </div>
</div>
<style>
  .admin-section {
    max-width: 800px;
    margin: 10vh auto;
  }

  .feature-placeholder {
    min-height: 150px;
    background: repeating-linear-gradient(
      45deg,
      #f0f0f0,
      #f0f0f0 10px,
      #e9ecef 10px,
      #e9ecef 20px
    );
    display: flex;
    align-items: center;
    justify-content: center;
    color: #6c757d;
    font-size: 1.2rem;
    border-radius: 0.5rem;
  }
</style>


