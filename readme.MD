# SASS - O que é ?

Um pré-processador CSS que irá dar poderes aos nossos estilos. Ele compila estrutura de código de `.scss`, `.sass` e `.css`

### Como usar ?

- Instalar o sass globalmente `npm i -g sass`
- Instalar extensão no VScode `live sass compiler`

### Organizar em pastas e arquivos

- Criar um arquivo (partials) com '\_' na frente, por exemplo `_base.scss`
- Importá-lo com `@import 'base`

Isso facilita a divisão do código em módulos para trabalharmos melhor

### Variáveis

```sass
  $variable: #fff;
```

### Encadeamento

```sass
  nav {
    ul {
      margin: 0;
      padding: 0;
      list-style: none;
    }

    li { display: inline-block; }

    a {
      display: block;
      padding: 6px 12px;
      text-decoration: none;
    }
  }
```

### @mixin

Mixin serve para fazer grupos de declarações CSS que podem ser reusadas conforme necessidade

```sass
  @mixin theme($theme: DarkGray) {
    background: $theme;
    box-shadow: 0 0 1px rgba($theme, .25);
    color: #fff;
  }

  .info {
    @include theme;
  }
```

### Condicionais

```sass
  @mixin text-effect($val) {
  @if $val == alert {
    color: yellow;
  }
  @else if $val == danger {
    color: red
  }
  @else {
    color: black
  }
}
```

### Repetições

```sass
  @for $i from 1 through 5 {
    .text-#{$i} {
      font-size: 10px * $i;
    }
  }

  $colors: (
    color1: yellow,
    color2: red,
    color3: black
  );

  @each $key, $color in $colors {
    .#{$color}-text {
      color: $color
    }
  }
```

### Funções

```sass
  lighten($color);
  darken($color)
```

### Herança

```sass
  .flex {
    display: flex;
    justify-content: center;
  }

  body {
    @extend .flex;
    align-items: center;
  }
```

### Hover

```sass
  p {
    color: red;

    &hover {
      color: blue;
    }
  }
```
