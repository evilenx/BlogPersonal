---
layout: post
title: Statusbar Dwm  
description: Statusbar que imprime fecha y hora para Dwm. 
---
{: .large}
# StatusBar - Dwm - Hecho en rust 

 ![Statusbardwm](/assets/images/statusbar.gif)
 *formato %d, %m, %Y, %T*

 Sin duda mi gestor de ventanas favoritos es Dwm. Aquí está el bloque de código para imprimir en pantalla la hora y fecha, ya que cuando lo instalé solo decía el nombre y la versión. 

Lo próximo que tengo que hacer, es imprimir en pantalla el estado de la batería, wifi, clima y los Mbs en uso. 

### Código en Rust 

```rust
use std::time::Duration;
use chrono::{DateTime, Local};

#[link(name = "X11")]
extern {
    fn XOpenDisplay(screen: usize) -> usize; 
    fn XStoreName(display: usize, window: usize, name: *const u8) -> i32;
    fn XDefaultRootWindow(display: usize) -> usize; 
    fn XFlush(display: usize) -> i32;
}

fn main() {
    let disp = unsafe { XOpenDisplay(0) };
    let root = unsafe { XDefaultRootWindow(disp) }; 

    loop {
        let local: DateTime<Local> = Local::now();

        let string = format!("{}\0", local.format("%d-%m-%Y %T.%3f"));

        unsafe { XStoreName(disp, root, string.as_ptr()); }
        unsafe { XFlush(disp); }

        std::thread::sleep(Duration::from_nanos((1e9 / 144.) as u64));
    }
}
```
