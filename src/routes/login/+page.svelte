<script>
  import { goto } from '$app/navigation';
  import { user } from '../../stores/auth.js';

  let nameInput = '';
  let emailInput = '';
  let error = '';

  const credencialesValidas = [
    { name: 'Sara', email: 'sara@email.com' },
    { name: 'Carlos', email: 'carlos@email.com' },
    { name: 'Admin', email: 'admin@site.com' }
  ];

  function iniciarSesion() {
    if (nameInput === '' || emailInput === '') {
      error = 'Por favor, completa todos los campos.';
      return;
    }

    const usuarioValido = credencialesValidas.find(
      (cred) => cred.name === nameInput && cred.email === emailInput
    );

    if (!usuarioValido) {
      error = 'Credenciales inválidas.';
      return;
    }

    user.set({
      name: nameInput,
      email: emailInput,
      loged: true
    });

    goto('/admin');
  }
</script>



<style>
  .login-container {
    max-width: 400px;
    margin: 10vh auto;
    padding: 2rem;
    border-radius: 1rem;
    background-color: #f8f9fa;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
  }
</style>

<div class="login-container">
  <h2 class="text-center mb-4">Iniciar sesión</h2>

  {#if error}
    <div class="alert alert-danger" role="alert">
      {error}
    </div>
  {/if}

  <div class="mb-3">
    <label for="nombre" class="form-label">Nombre</label>
    <input
      id="nombre"
      class="form-control"
      placeholder="Ej: Sara"
      bind:value={nameInput}
    />
  </div>

  <div class="mb-3">
    <label for="email" class="form-label">Correo electrónico</label>
    <input
      id="email"
      type="email"
      class="form-control"
      placeholder="Ej: sara@email.com"
      bind:value={emailInput}
    />
  </div>

  <button class="btn btn-primary w-100" on:click={iniciarSesion}>
    Entrar
  </button>
</div>
