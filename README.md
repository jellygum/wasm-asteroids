# Asteroids 

This is a WebAssembly port of an [Asteroids game written in C](https://github.com/flightcrank/asteroids):

![Screenshot of asteroids game](https://raw.githubusercontent.com/robertaboukhalil/wasm-asteroids/master/screenshot.png)

If you're looking for a practical guide to learning WebAssembly, check out my book [Level up with WebAssembly](http://www.levelupwasm.com/).

## Build

Fetch Emscripten from DockerHub:

```bash
docker pull robertaboukhalil/emsdk:1.38.26
```

Create a container from that image:

```bash
# Create container from that image
docker run -dt --name wasm robertaboukhalil/emsdk:1.38.26

# Enter the container
docker exec -it wasm bash
```

Within the container, fetch the code:

```bash
git clone "https://github.com/robertaboukhalil/wasm-asteroids.git"
cd wasm-asteroids
```

And compile it to WebAssembly:

```bash
emcc \
    -o app.html asteroids/*.c \
    -Wall -g -lm \
    -s USE_SDL=2
```
