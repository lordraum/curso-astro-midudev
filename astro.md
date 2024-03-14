# AstroJS

## Características

### Islas

Son bloques dinámicos dentro de una arquitectura estática, es decir son bloques de código dentro de una web estática que necesitan código js para funcionar. Por lo tanto Astro no cargo JS en el cliente.

### Framework agnóstico

Astro se puede utilizar con múltiples bibliotecas frontend como React, Vue, Svelte, Vanilla, s sin bibliotecas.

## Primeros pasos

Instalación --> `pnpm create astro@latest`
Extensión VsCode --> Astro oficial

## Sistema de archivos

astro.config.mjs --> Configuración de astro --> Por ejemplo añadir integraciones ()

src/env.d.ts --> Archivo de typing de Astro

### Layouts

Componente que envuelve partes de la app, funcionan como plantilla.

### Pages

Carpeta que tendrá los archivos que serán las rutas

## Sintáxis

Similar a JSX, pero no es la misma.

### Bloque JS

Al iniciar el archivo se delimita la isla con tres guiones arriba y abajo:

```astro
---
import Layout from '../layouts/Layout.astro'
import Card from '../components/Card.astro'
---
```

### Componentes

```js
// Crear --> Hello.Astro
---
const {name} = Astro.props
---
<h1>¡Hola, {name}!</h1>
  
// Montar --> Example.Astro
---
import Hello from "../components/Hello.astro";
---
<main>
  <Hello name="Alejandra" />
  <Hello name="Juan" />
  <p>¡Hola a todos!</p>
</main>
```

### Props

```astro
---
// para typescript
interface Props {
	title: string;
	body: string;
	href: string;
}

// typescript y js
const { href, title, body } = Astro.props;
---
```

### Estilos

Los componentes incluyen su sección de estilos.

**Scope interno** --> el estilo solo funciona para los elementos del componente.

```html
<style>
  h1 {
  color: 'green';
  }
</style>

<!-- Este estilo solo se aplicará al h1 del componente -->
```

**Scope global** --> el estilo se aplica a todos los elementos a los que aplique el selector.

```html
<style is:global>/* Directiva */
	:root {
		--accent: 136, 58, 234;
		--accent-light: 224, 204, 250;		
	}
</style>
```

**Directivas**

Instrucción adicional, ejemplo --> is:global, is:inline

### Variable global Astro

Contiene información y realiza acciones, ejemplos --> `Astro.props`, `Astro.params`

<!-- https://youtu.be/RB5tR_nqUEw?t=1564 -->

## Sistema de ingraciones

Astro tiene muchas integraciones preestablecidas, a la lista se accede con `pnpn astro add --help`

### Tailwind

`pnpm astro add tailwind`






