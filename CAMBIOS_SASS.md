# Documento de Cambios SASS - UrbanWear

## Actividad 3.1 - Caso Práctico Bootstrap - Implementando con SASS

---

## 1. Fichero `scss/_variables.scss`

### Colores por defecto de Bootstrap modificados:
```scss
$primary:   #1a1a2e;    // Azul oscuro elegante (antes: #0d6efd)
$secondary: #16213e;    // Azul profundo (antes: #6c757d)
$success:   #0f3460;    // Azul medio (antes: #198754)
$info:      #e94560;    // Rojo/coral acento (antes: #0dcaf0)
$warning:   #f5a623;    // Amarillo dorado (antes: #ffc107)
$danger:    #d63031;    // Rojo intenso (antes: #dc3545)
$dark:      #0a0a0a;    // Negro puro (antes: #212529)
```

### Tipografías personalizadas:
```scss
$font-family-base: 'Open Sans', 'Segoe UI', sans-serif;
$headings-font-family: 'Montserrat', 'Segoe UI', Arial, sans-serif;
$headings-font-weight: 700;
```

### Variables de formularios:
```scss
$input-border-radius: 8px;
$input-border-color: #dfe6e9;
$input-focus-border-color: #e94560;
$input-focus-box-shadow: 0 0 0 0.2rem rgba(233, 69, 96, 0.25);
$input-bg: #ffffff;
$form-check-input-checked-bg-color: #e94560;
```

### Variables de cards:
```scss
$card-border-radius: 12px;
$card-spacer-x: 1.5rem;
$card-border-color: rgba(0, 0, 0, 0.08);
```

### Variables de botones:
```scss
$btn-border-radius: 25px;
$btn-font-weight: 600;
```

### Variables de modales:
```scss
$modal-content-border-radius: 16px;
$modal-content-border-width: 0;
$modal-backdrop-opacity: 0.6;
```

### Variables de alertas:
```scss
$alert-border-radius: 12px;
$alert-border-width: 0;
```

### Variables de dropdown:
```scss
$dropdown-border-radius: 12px;
$dropdown-border-width: 0;
$dropdown-box-shadow: 0 8px 30px rgba(0, 0, 0, 0.12);
$dropdown-link-hover-bg: rgba(233, 69, 96, 0.08);
$dropdown-link-hover-color: #e94560;
```

---

## 2. Fichero `scss/_reboot.scss`

```scss
h1, h2, h3, h4, h5, h6 {
  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
  letter-spacing: -0.02em;
  color: #1a1a2e;
}

h2::after {
  content: '';
  width: 50px;
  height: 3px;
  background: #e94560;
}

p {
  color: #636e72;
  line-height: 1.8;
}

a:hover {
  color: #e94560;
}

::selection {
  background-color: rgba(233, 69, 96, 0.2);
}
```

---

## 3. Fichero `scss/_navbar.scss`

- Cambio de color al pasar ratón: `&:hover { color: #e94560; }`
- Subrayado animado con `::after` que aparece al hover
- Estado activo con fondo semitransparente
- Dropdown con animación `fadeInDown`, bordes redondeados y hover con desplazamiento
- Brand con efecto scale en el icono al hover

---

## 4. Fichero `scss/_forms.scss`

- Bordes: `2px solid #dfe6e9` → Focus: `#e94560`
- Fondo: `#fafafa` → Focus: `#ffffff`
- Placeholder en cursiva con color `#b2bec3`
- Checkbox/Radio checked: `background-color: #e94560`
- Box-shadow en focus: `rgba(233, 69, 96, 0.15)`
- Validación con colores personalizados

---

## 5. Fichero `scss/_modals.scss`

- Border-radius: `16px`
- Animación: scale + translateY al aparecer
- Header con gradiente: `linear-gradient(135deg, #1a1a2e, #16213e)`
- Variante success: gradiente verde `#00b894 → #00cec9`
- Backdrop con `blur(4px)`
- Footer con botones redondeados

---

## 6. Fichero `scss/_alerts.scss`

- Sin borde: `border: none`
- Barra lateral decorativa con `::before` (4px de ancho)
- Colores de fondo suaves por variante
- Border-radius: `12px`
- Box-shadow sutil
- Heading con Montserrat bold

---

## 7. Fichero `scss/_cards.scss` y `scss/_custom.scss`

- Cards con hover: `translateY(-8px)` + sombra ampliada
- Imagen zoom al hover: `scale(1.05)`
- Botones con gradientes y efectos de elevación
- Hero slides con gradientes oscuros personalizados
- Carousel indicators circulares con borde
- Footer con gradiente y hover con color coral
- Paginación, breadcrumb, accordion, badges personalizados
