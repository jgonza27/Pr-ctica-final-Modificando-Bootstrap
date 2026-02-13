# Documentación de cambios SCSS — Proyecto NexusHub

## Fichero `_variables.scss`

Sobrescrituras de variables por defecto de Bootstrap **antes** de importar la librería.

### Colores personalizados
```scss
$primary:       #1a73e8;    // Azul vibrante (reemplaza el azul por defecto)
$secondary:     #6c5ce7;    // Púrpura
$success:       #00b894;    // Verde esmeralda
$danger:        #e74c3c;    // Rojo intenso
$warning:       #fdcb6e;    // Amarillo cálido
$info:          #00cec9;    // Turquesa
$light:         #f8f9fc;    // Gris muy claro
$dark:          #0f1923;    // Casi negro
```

### Tipografía
```scss
$font-family-sans-serif: "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
$headings-font-family:   "Outfit", "Inter", sans-serif;
$headings-font-weight:   700;
$font-size-base: 1rem;
$h1-font-size:   2.75rem;
$h2-font-size:   2.25rem;
$h3-font-size:   1.75rem;
```

### Border radius global
```scss
$border-radius:    0.75rem;
$border-radius-sm: 0.5rem;
$border-radius-lg: 1rem;
$border-radius-pill: 50rem;
```

### Botones
```scss
$btn-border-radius:    0.75rem;
$btn-padding-y:        0.6rem;
$btn-padding-x:        1.5rem;
$btn-font-weight:      600;
```

### Navbar
```scss
$navbar-padding-y:              1rem;
$navbar-dark-color:             rgba(255, 255, 255, 0.85);
$navbar-dark-hover-color:       #fff;
$navbar-dark-active-color:      #fff;
$navbar-dark-toggler-border-color: rgba(255, 255, 255, 0.2);
```

### Formularios
```scss
$input-bg:                    #f8f9fc;
$input-border-color:          #d1d9e6;
$input-border-radius:         0.75rem;
$input-focus-border-color:    $primary;
$input-focus-box-shadow:      0 0 0 0.2rem rgba($primary, 0.2);
$input-padding-y:             0.7rem;
$input-padding-x:             1rem;
$form-label-font-weight:      600;
$form-label-margin-bottom:    0.4rem;
```

### Cards
```scss
$card-border-radius:   1rem;
$card-border-color:    transparent;
$card-spacer-x:        1.5rem;
$card-spacer-y:        1.5rem;
$card-cap-padding-y:   1rem;
$card-cap-bg:          transparent;
```

### Modal
```scss
$modal-content-border-radius:  1rem;
$modal-content-border-color:   transparent;
$modal-header-border-color:    rgba(0, 0, 0, 0.06);
$modal-footer-border-color:    rgba(0, 0, 0, 0.06);
$modal-content-bg:             #ffffff;
$modal-backdrop-opacity:       0.6;
```

### Alertas
```scss
$alert-border-radius:  0.75rem;
$alert-padding-y:      1rem;
$alert-padding-x:      1.25rem;
```

### Sombras
```scss
$box-shadow:    0 4px 24px rgba(0, 0, 0, 0.08);
$box-shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.06);
$box-shadow-lg: 0 8px 40px rgba(0, 0, 0, 0.12);
```

---

## Fichero `_reboot.scss`

Estilos de reseteo aplicados **después** de Bootstrap para ajustar los elementos base.

```scss
body {
  background-color: #f0f2f5;
  color: #2d3436;
  line-height: 1.7;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

h1, h2, h3, h4, h5, h6 {
  color: #0f1923;
  letter-spacing: -0.02em;
  line-height: 1.2;
}

h1 { font-weight: 800; }
h2 { font-weight: 700; margin-bottom: 1rem; }
h3 { font-weight: 600; }

p {
  color: #636e72;
  line-height: 1.8;
  margin-bottom: 1rem;
}

a {
  color: #1a73e8;
  text-decoration: none;
  transition: color 0.3s ease;
  &:hover { color: #1557b0; }
}

::selection {
  background-color: #1a73e8;
  color: #fff;
}

html { scroll-behavior: smooth; }
section { padding: 5rem 0; }
```

---

## Fichero `_custom.scss`

Estilos personalizados adicionales para cada componente.

### Navbar — Efectos hover, dropdown y scroll
```scss
.navbar {
  backdrop-filter: blur(12px);
  transition: all 0.4s ease;
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);

  .nav-link {
    font-weight: 500;
    border-radius: 0.5rem;
    transition: all 0.3s ease;
    &:hover {
      background-color: rgba(255, 255, 255, 0.1);
      color: #fff !important;
      transform: translateY(-1px);
    }
    &.active {
      background-color: rgba($primary, 0.2);
    }
  }

  .dropdown-menu {
    border: none;
    border-radius: 0.75rem;
    box-shadow: 0 10px 40px rgba(0, 0, 0, 0.15);
    animation: dropdownFadeIn 0.3s ease;
    .dropdown-item {
      border-radius: 0.5rem;
      transition: all 0.25s ease;
      &:hover {
        background-color: rgba($primary, 0.08);
        color: $primary;
        transform: translateX(4px);
      }
    }
  }
}

// Animación dropdown
@keyframes dropdownFadeIn {
  from { opacity: 0; transform: translateY(-8px); }
  to   { opacity: 1; transform: translateY(0); }
}

// Efecto scroll
.navbar.scrolled {
  background-color: rgba(15, 25, 35, 0.95) !important;
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.2);
}
```

### Botones — Gradientes y hover
```scss
.btn {
  font-weight: 600;
  transition: all 0.3s ease;
  &:hover { transform: translateY(-2px); box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15); }
}

.btn-primary {
  background: linear-gradient(135deg, $primary, darken($primary, 10%));
  border: none;
  &:hover { box-shadow: 0 6px 20px rgba($primary, 0.35); }
}
```

### Cards — Efecto hover lift
```scss
.card {
  border: none;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.06);
  transition: all 0.4s ease;
  &:hover { transform: translateY(-8px); box-shadow: 0 12px 40px rgba(0, 0, 0, 0.12); }
}
```

### Formularios — Focus personalizado
```scss
.form-control, .form-select {
  transition: all 0.3s ease;
  border: 2px solid #d1d9e6;
  &:hover { border-color: #b2bec3; }
  &:focus {
    border-color: $primary;
    box-shadow: 0 0 0 0.2rem rgba($primary, 0.15);
    background-color: #fff;
  }
}
```

### Modales — Cabecera gradiente y animación
```scss
.modal .modal-header {
  background: linear-gradient(135deg, $primary, $secondary);
  color: #fff;
  border-bottom: none;
}

.modal.fade .modal-dialog {
  transform: scale(0.9) translateY(-20px);
  transition: transform 0.35s ease;
}
.modal.show .modal-dialog {
  transform: scale(1) translateY(0);
}
```

### Alertas — Borde lateral y animación de entrada
```scss
.alert {
  border: none;
  border-left: 4px solid;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.06);
  animation: alertSlideIn 0.4s ease;
}

.alert-success { background-color: #eafaf1; border-left-color: $success; color: #1a5c32; }
.alert-danger  { background-color: #fdf0ef; border-left-color: $danger;  color: #922820; }
.alert-warning { background-color: #fef9e7; border-left-color: $warning; color: #7d6608; }
.alert-info    { background-color: #e8f8f5; border-left-color: $info;    color: #0e6655; }

@keyframes alertSlideIn {
  from { opacity: 0; transform: translateX(-20px); }
  to   { opacity: 1; transform: translateX(0); }
}
```

### Hero Section — Gradiente con efecto glow
```scss
.hero-section {
  background: linear-gradient(135deg, #0f1923 0%, #1a2a3a 40%, #1a73e8 100%);
  min-height: 100vh;
  // Decoraciones animadas con pseudo-elementos ::before y ::after
}
```

### Footer — Estilo oscuro con enlaces animados
```scss
.footer {
  background: linear-gradient(135deg, #0f1923 0%, #1a2a3a 100%);
  .footer-link {
    transition: all 0.3s ease;
    &:hover { color: #fff; padding-left: 5px; }
  }
  .footer-social a {
    &:hover { background-color: $primary; transform: translateY(-3px); }
  }
}
```

---

## Fichero `main.scss`

Punto de entrada que define el orden de importación:

```scss
// 1. Variables personalizadas (ANTES de Bootstrap)
@import "variables";

// 2. Bootstrap completo
@import "../node_modules/bootstrap/scss/bootstrap";

// 3. Estilos propios (DESPUÉS de Bootstrap)
@import "reboot";
@import "custom";
```
