<script>
	import { user } from '../stores/auth.js';
</script>

<nav class="navbar navbar-expand-lg bg-body-tertiary">
	<div class="container-fluid">
		<a class="navbar-brand" href="/">SR</a>
		<button
			class="navbar-toggler"
			type="button"
			data-bs-toggle="collapse"
			data-bs-target="#navbarSupportedContent"
			aria-controls="navbarSupportedContent"
			aria-expanded="false"
			aria-label="Toggle navigation"
		>
			<span class="navbar-toggler-icon"></span>
		</button>
		<div class="collapse navbar-collapse" id="navbarSupportedContent">
			<ul class="navbar-nav me-auto mb-2 mb-lg-0">
				<li class="nav-item">
					<a class="nav-link active" aria-current="page" href="/">Inicio</a>
				</li>
				<li class="nav-item">
					<a class="nav-link" href="/admin">Administrador</a>
				</li>
                <li class="nav-item">
					<a class="nav-link" href="/platillos">Platillos</a>
				</li>
				<li class="nav-item ms-auto mb-2 mb-lg-0">
					{#if $user.loged}
                    <a class="btn btn-outline-danger btn-sm" href="/logout">Cerrar sesión</a>

					{:else}
						<a href="/login " class="btn btn-outline-success btn-sm ">Iniciar sesión</a>
					{/if}
				</li>
			</ul>
			<form class="d-flex" role="search">
				<input class="form-control me-2" type="search" placeholder="Search" aria-label="Search" />
				<button class="btn btn-outline-success" type="submit">Search</button>
			</form>
		</div>
	</div>
</nav>