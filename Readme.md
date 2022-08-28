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

Agregar una nueva carpeta `assets` y dentro agregamos las imagenes [assets.zip](https://drive.google.com/drive/folders/1Gg1kFfple_9cM0slGHb6fumXu3JMSVAG)

## Referencias

Bevy requiere de ciertas [librerías](https://github.com/bevyengine/bevy/blob/main/docs/linux_dependencies.md) en el sistema, sin estas no compila.

[Bevy Book](https://bevyengine.org/learn/book/introduction/)
[Docs](https://docs.rs/bevy/latest/bevy/)
[Bevy Learn](https://bevyengine.org/learn/)
[Bevy Examples](https://bevyengine.org/examples/)
