# Videojuego con rust

- Creando el videojuego del pom, con la ayuda del framework Bevy.
- Crear un proyecto nuevo `cargo new rust-pong`
- Se ha agregado en el fichero `Cargo.toml`

```r
[dependencies]
rand = "0.8.0"
bevy = "0.5"
heron = { version = "0.12.1", default-features = false, features = ["2d"] }
```

<<<<<<< Updated upstream
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
=======
Agregar una nueva carpeta `assets` y dentro agregamos las imagenes [assets.zip](https://drive.google.com/drive/folders/1Gg1kFfple_9cM0slGHb6fumXu3JMSVAG)
>>>>>>> Stashed changes
