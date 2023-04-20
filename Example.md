# Typora Example

This is a *simple* **example** of some **Markdown** to illustrate the power of Typora from https://typora.io. Look at this text using a plain text editor (e.g., Notepad or Vim) and Typora. I have included exported versions of this text unaltered with this.

Insert a table of contents by removing the X in the following (Click to jump):

[tocX]

## Basics

You can create **bold**, *italic*, ***bold-italic***, <u>underlined</u>, ==highlighted==, or even `inline code` as you write using familiar editing sequences, such as in Microsoft Word. Footnotes[^1] are possible. Control/Command-click on the footnote to jump directly to it.

> Or quotations of something off the web. URLs such as https://www.doulos.com is automatically figured out.
>

<img src="Example.assets/doulos_logo_200px.png" alt="doulos_logo_200px" style="zoom:25%;" />Copyright © 2023 Doulos Ltd. All rights reserved.



#### Math equations are [relatively easy](https://support.typora.io/Math/) :

$\lim_{x \to \infty} \exp(-x) = 0$

$magnitude = \sqrt{x^2 + y^2}$

$power = \int_{t=0}^{n}v_t f(t)$

#### Lists

Allowing slides with

- Bullets
  - And sub-bullets

1. Such as this
   1. Even ordered lists
   1. Numbering is automatic
2. At different levels
   - Or unordered sub-lists

- [ ] Tasks
  - [ ] With things to do
  - [x] Can be checked off

#### Tables are a breeze

| Terminology | Meaning                                    |
| ----------- | ------------------------------------------ |
| Ordered     | Numbered items automatically updated       |
| Unordered   | Bulleted lines used for lists              |
| Tasks       | Check boxes that can be easily checked off |

#### Graphics images

Supported either locally or from the web with scaling allowed. Usually, just drag-n-drop.

- Example 1, a simple PNG (jpeg works too). The graphic needs to be sent with the Markdown, usually in a folder named DOCNAME.assets.

<img src="Example.assets/the_hitchhikers_guide_to_the_galaxy.jpg" alt="the_hitchhikers_guide_to_the_galaxy" style="zoom:25%;" />

#### Embedded videos:

<!-- Change iframe to xframe in the following to allow export in Word -->

<iframe width="560" height="315" src="https://www.youtube.com/embed/K1gKJdC4WYA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


For complex stuff, you can use HTML natively, such as <span style="color:red;">RedText</span>.

## Source Code

You can also create code blocks, as shown below. There are MANY languages supported. I include samples of some that we use here.

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

### Rust

```rust
fn main() {
    println!("Hello World!");
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



## Diagrams

Diagrams are supported using [mermaid](https://mermaid.js.org/intro/) using an extension to Markdown. Simply enter a code block using the language `mermaid` and start with an type indicator. Here are some examples.

### Flow Charts

Using a `mermaid` code-block show a `flowchart` thusly.

```mermaid
---
title: Receive password
---
flowchart LR
  Start(("passwd"))
  style Start fill:#20,stroke:#200,stroke-width:3px
  Fail(((Fail)))
  style Fail fill:#0,stroke:#200,stroke-width:3px
  Pass(((Pass)))
  style Pass fill:#0,stroke:#200,stroke-width:3px
  Start --> Init[count=0]
  Init  --> Read[[Read]]
  Read  --> Inc[count++]
  Inc --> Choice{choice}
  Choice -->|count>=maxTries|Lock
  Choice -->|Enter| Check[[Check]]
  Choice -->|Abort| Fail
  Choice -->|Reset password| SendRequest[[Email password]]
  SendRequest --> Read
  Check --> Match{Match}
  Match -->|Yes|Pass
  Match -->|No|Read
  Lock[[lock account]] -->Fail


```

### UML

#### Sequence diagrams

Using a `mermaid` code-block show a `sequenceDiagram` thusly.

```mermaid
sequenceDiagram
  Activate Client
  Client->>Server: Hello, Negotiate connection
  activate Server
  Server->>Client: Hello, Negotiate connection
  Note over Client,Server: Negotiate parameters
  Note over Client,Server: Communicate data
  Note over Client,Server: Teardown
  deactivate Server
  deactivate Client
```

#### Class diagrams

Using a `mermaid` code-block show a `classDiagram` thusly.

```mermaid
---
SystemC
---
classDiagram
  class sc_object {
    +name() string
  }
  class sc_interface {
    +default_event() const sc_event&
  }
  class sc_port~sc_fifo_out_if~ {
    +operator->() sc_fifo_out_if*
    -m_port sc_fifo_out_if*
  }
  class sc_port~sc_fifo_in_if~ {
    +operator->() sc_fifo_in_if*
    -m_port sc_fifo_in_if*
  }
  class sc_prim_channel {
    +request_update() void
    +update() void
  }
  class sc_fifo_out_if~T~ {
    +write(T const&)* void
    +nb_write(T)* bool
    +num_free()* int
    +data_read_event()* sc_event const&
  }
  class sc_fifo_in_if~T~ {
    +read()* T const&
    +nb_read(T&)* bool
    +num_available()* int
    +data_written_event()* sc_event const&
  }
  class MODULE {
    +port1 sc_port~sc_out_if~
    +port2 sc_port~sc_in_if~
    +thread() void
  }
  class sc_fifo~T~ {
    +write(T const&) void
    +read() T
    +nb_write(T const&) bool
    +nb_read(T&) bool
    +data_read_event() sc_event const&
    +data_written_even() sc_event const&
    +num_free() int
    +num_available() int
    -m_write_evt sc_event
    -m_read_evt sc_event
    -m_data std::deque<TYPE>
  }
  class TOP {
    +mod1 MODULE
    +fifo1 sc_fifo~T~
    +method() void
  }
  sc_object <|-- sc_module
  sc_object <|-- sc_prim_channel
  sc_object <|-- sc_port~sc_fifo_in_if~
  sc_object <|-- sc_port~sc_fifo_out_if~
  sc_interface <|-- sc_fifo_in_if~T~
  sc_interface <|-- sc_fifo_out_if~T~
  sc_port~sc_out_if~ *-- sc_interface
  sc_prim_channel <|-- sc_fifo~T~
  sc_fifo_out_if~T~ <|-- sc_fifo~T~
  sc_fifo_in_if~T~ <|-- sc_fifo~T~
  sc_fifo_out_if~T~ <.. sc_port~sc_fifo_out_if~
  sc_fifo_in_if~T~ <.. sc_port~sc_fifo_in_if~
  sc_module <|-- MODULE
  sc_module <|-- TOP
  TOP *-- MODULE
  TOP *-- sc_fifo~T~
  MODULE *-- sc_port~sc_out_if~
  MODULE *-- sc_port~sc_in_if~
 
```

#### State diagrams

Using a `mermaid` code-block show a `stateDiagram` thusly.

```mermaid
stateDiagram
  [*] --> Idle : Power on
  Idle --> Process: "Enter pressed"
  Idle --> AppendChar : "Other"
  AppendChar --> Idle
  state Process <<choice>>
  Process --> Idle : Entered != Password
  Process --> Lock : Locked == false
  Process --> Unlock : Locked == true
  Lock --> Idle
  Unlock --> Idle
  Idle --> [*] : Power off
```

### Pie charts

Using a `mermaid` code-block show a `pie` thusly.

```mermaid
pie
    title Program Language Popularity - 2023
    "Python - up 0.16%"       : 15.49
    "C - up 1.31%"            : 15.39
    "C++ - up 5.93%"          : 13.94
    "Asm - down 0.21%"        :  1.38
    "Perl - down 0.01%"       :  0.79
    "Rust - up 0.16%"         :  0.70
    "Other"                   : 47.95
```



### Mindmap

```mermaid
mindmap
  root((Documentation))
    Course
    	Manual
    	  Powerpoint
    	  PDF
    	Workbook
    	  Word
    	  PDF
    Webinar
      Powerpoint
```

[^1]: This is a simple example of a footnote.

### Waveforms

For now, it has to be a simple graphic generated with [WaveDrom](https://wavedrom.com). However, support for WaveDrom has been requested and should not be too difficult to incorporate.

![APB-TLM2-waves](Example.assets/APB-TLM2-waves.jpg)

## That's all folks
