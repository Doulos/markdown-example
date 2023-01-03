# Typora Example

This is a *simple* example of some **Markdown** to illustrate the power of Typora from https://typora.io. Look at this text using a plain text editor (e.g., Notepad or Vim) and Typora. I have included exported versions of this text unaltered with this.

Insert a table of contents (Click to jump):

[toc]

## Basics

You can create **bold**, *italic*, ***bold-italic***, <u>underlined</u>, ==highlighted==, or even `inline code` as you write using familiar editing sequences, such as in Microsoft Word. Footnotes[^1] are possible.

> Or quotations of something off the web. URLs such as https://www.doulos.com is automatically figured out.
>

Copyright © 2023 Doulos Ltd. All rights reserved.



![doulos_logo_200px](Typora%20Example.assets/doulos_logo_200px.png)

#### Math equations are [relatively easy](https://support.typora.io/Math/) :

$\lim_{x \to \infty} \exp(-x) = 0$

$magnitude = \sqrt{x^2 + y^2}$

#### Lists

Allowing slides with

- Bullets
  - And sub-bullets

1. Such as this
   1. Even ordered lists
2. And automatically updated
   - Or unordered sub-lists

#### Tables are a breeze

| Terminology | Meaning                                    |
| ----------- | ------------------------------------------ |
| Ordered     | Numbered items automatically updated       |
| Unordered   | Bulleted lines used for lists              |
| Tasks       | Check boxes that can be easily checked off |

#### Graphics images

Supported either locally or from the web with scaling allowed. Usually, just drag-n-drop.

<img src="Typora%20Example.assets/the_hitchhikers_guide_to_the_galaxy.jpg" alt="the_hitchhikers_guide_to_the_galaxy" style="zoom:25%;" />

#### Embedded videos:

<video src=myvid.mp4 />

For complex stuff, you can use HTML natively, such as <span style="color:red;">RedText</span>.

## Source Code

You can also create code blocks, as shown below.

### VHDL

```vhdl
use std.textio.all;

entity hello_world is
end hello_world;

architecture behaviour of hello_world is
begin
    process
    begin
       write (output, String'("Hello world!"));
       wait;
    end process;
end behaviour;
```

### SystemVerilog

```systemverilog
module hello_world;
  initial begin
    $display( "Hello world!" );
  end
endmodule
```

### C

```c
#include <stdio.h>
int main() {
  printf( "Hello world!\n" );
}
```

### C++

```c++
#include <format> // C++20
int main() {
  std::print( "Hello world!\n" );
}
```

### Python

```python
#!/usr/bin/env python
print "Hello World!"
```

### Bash

```bash
#!/usr/bin/env bash
echo "Hello world!"
```

### TCL

```tcl
#!/usr/bin/env tclsh
puts "Hello world!"
```

### Assembly

```assembly
.section ".text"
__start:
    ADD r0, r0, lsl #2  // r0 *= 5;
    BX LR
.end  
```

[^1]: This is a simple example of a foot note.

## That's all