# Videojuego con rust

- Creando el videojuego del pom, con la ayuda del framework Bevy.
- Crear un proyecto nuevo `cargo new rust-pong`
- Se ha agregado en el fichero `Cargo.toml` esto para la versión web

```r
[lib]
crate-type = ["cdylib", "rlib"]

[dependencies]
wasm-bindgen = "0.2"
rand = "0.8.0"
heron = { version = "0.12.1", default-features = false, features = ["2d"] }

# native
[target.'cfg(not(target_arch = "wasm32"))'.dependencies]
bevy = "0.5"

# wasm
[target.'cfg(target_arch = "wasm32")'.dependencies]
bevy = {version = "0.5", default-features = false, features = ["bevy_winit", "render"]}
bevy_webgl2 = "0.5"
```

- Agregar una nueva carpeta `assets` y dentro agregamos las imagenes [assets.zip](https://drive.google.com/drive/folders/1Gg1kFfple_9cM0slGHb6fumXu3JMSVAG)

- Actualizar una dependencia con este comando `cargo update -p tracing-wasm --precise 0.2.0` para que no de errores de compilación

- Agregar un fichero `build.sh` para que haga la compilación y levante el servidor

```sh
wasm-pack build --target web
rm -rf web/pkg
mv pkg web

rm -rf web/assets
cp -r assets web
python3 -m http.server 8089 -d web
```

## Referencias

Bevy requiere de ciertas [librerías](https://github.com/bevyengine/bevy/blob/main/docs/linux_dependencies.md) en el sistema, sin estas no compila.

[Bevy Book](https://bevyengine.org/learn/book/introduction/)
[Docs](https://docs.rs/bevy/latest/bevy/)
[Bevy Learn](https://bevyengine.org/learn/)
[Bevy Examples](https://bevyengine.org/examples/)
