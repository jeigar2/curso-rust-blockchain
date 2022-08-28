# Conectando rust con el navegador

- Para conectar el lenguaje rust con el navegador se realizan los siguientes pasos:
  - Se ha crea un proyecto desde el terminal con el flag `lib`
    - Comando completo: `cargo new --lib rust-wasm`

  - Se ha agregado en el fichero `Cargo.toml`
    - Seccion nueva `[lib]`
      - agregado la linea `crate-type = ["cdylib", "rlib"]`
    - Sección `[dependencies]`
      - agregada la línea `wasm-bindgen = "0.2.82"`
  - Se ha instalado desde el terminal en el proyecto `wasm-pack build --target web`

Fichero Cargo.toml

```r
[lib]
crate-type = ["cdylib", "rlib"]

[dependencies]
wasm-bindgen = "0.2.82"
```

Se ha creado una libreria de rust

```rs
use wasm_bindgen::prelude::*;

#[wasm_bindgen]
extern {
    pub fn alert(s: &str);
}

#[wasm_bindgen]
pub fn saludar(nombre: &str){
    alert(&format!("Hola, {}, ¿Cómo estás?", nombre));
}
```

Se ha creado una pagina html, que hace uso de rust.

index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi primer proyecto en WASM</title>
    <script type="module">
        import init, {saludar} from "./pkg/rust_wasm.js"
        init().then(()=> {
            saludar("Ignacio");
        });
    </script>
</head>
<body>
    
</body>
</html>
```

Para ejecutarlo en un servidor desde un terminal se ejecuta el el comando `python3 -m http.server 8099`

Abrir un navegado con la url localhost:8099

## Referencias

- Curso Básico de Rust: Variables, Ciclos y Funciones - Platzi
  - https://platzi.com/cursos/rust-basico/
- Funciones lambda - Platzi
  - https://platzi.com/clases/1826-java-funcional/26225-funciones-lambda/
