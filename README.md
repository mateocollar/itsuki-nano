# itsuki-nano

Resaltado de sintaxis de [Itsuki](https://github.com/Apolo1061/itsuki-lang) para el editor GNU nano. Archivos `.suki` y `.huki`.

Basado en el esquema de colores del resaltado de C incluido en nano.

## Instalación

### Usuario (recomendado)

```bash
mkdir -p ~/.nano
cp itsuki.nanorc ~/.nano/itsuki.nanorc
echo 'include "~/.nano/itsuki.nanorc"' >> ~/.nanorc
```

Si el archivo `~/.nanorc` no existe, la última línea lo crea.

### Sistema (todos los usuarios)

Linux:

```bash
sudo cp itsuki.nanorc /usr/share/nano/itsuki.nanorc
echo 'include "/usr/share/nano/itsuki.nanorc"' | sudo tee -a /etc/nanorc
```

Windows (nano para Windows, por ejemplo vía MSYS2):

```bash
mkdir -p /usr/share/nano
cp itsuki.nanorc /usr/share/nano/itsuki.nanorc
echo 'include "/usr/share/nano/itsuki.nanorc"' >> /etc/nanorc
```

### Verificación

```bash
nano test_fsuki.suki
```

El resaltado se aplica de forma automática: nano detecta los archivos `.suki` y `.huki` por su extensión, sin configuración adicional.

## Colores

| Color | Elementos |
|---|---|
| Verde | Tipos (`int`, `float`, `double`, `char`, `bool`, `void`, `int8`-`int64`), declaraciones (`var`, `const`, `struct`, `union`, `enum`, `typedef`, `extern`, `inline`) y visibilidad (`class`, `namespace`, `public`, `private`, `protected`, `this`, `using`) |
| Amarillo brillante | Control de flujo (`fn`, `if`, `else`, `while`, `for`, `do`, `switch`, `case`, `default`) y cadenas de texto, incluidas las interpoladas (`f"..."`, `$"..."`) |
| Magenta | Saltos de control (`return`, `break`, `continue`, `goto`) |
| Magenta brillante | Literales de carácter (`'A'`) |
| Cyan brillante | Directivas del preprocesador (`#include`, `#define`, `#pragma`, `#ifdef`, `#ifndef`, `#endif`) |
| Cyan | `true`, `false` y `__asm__` |
| Rojo brillante | Constantes y valores de enum en mayúsculas (`MAX_BUFFER`, `ACTIVO`) |
| Azul brillante | Comentarios de línea (`//`) y de bloque (`/* */`) |
| Amarillo | Marcadores `FIXME`, `TODO`, `XXX` |
| Verde (fondo) | Espacios en blanco al final de la línea |

Los colores finales dependen del tema de la terminal: `bright` se mapea a la versión intensa del color del terminal.

## Archivos

```
itsuki-nano/
├── itsuki.nanorc
├── LICENSE
└── README.md
```

## Mantenedor

[Mateo Collar](https://github.com/mateocollar)

## Licencia

MIT
