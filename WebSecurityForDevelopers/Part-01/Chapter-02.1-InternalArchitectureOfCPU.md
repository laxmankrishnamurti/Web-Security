# Internal Architecture of the CPU

Let's begin to learn about the internal architecture of central processing unit which is the brain of a computer.

**1. On top we have a cover called an _integrated heat spreader_**

[Integrated heat spreader](https://drive.google.com/file/d/1pkBSmtNnAGRwefi6WmC_kroar_eZuV_a/view?usp=sharing)

**2. And inside is a smaller metal package that holds the _integrated circuit_ which is technically called a _die_. This die is mounted on a _PCB(Printed circuit board)_ that distributes the _1200 connection_ points to landing pads that interface with the landing grid array on the motherboard.**

[Metal package](https://drive.google.com/file/d/1hvrferzPzGdl97mAuGB0g0wbq60U_rQu/view?usp=sharing)
[Integrated Circuit -> Die](https://drive.google.com/file/d/1HA-N2Zb8G88wyUuaytmSARYrxeOgKQEX/view?usp=sharing)
[PCB](https://drive.google.com/file/d/1RdtAZJw5O_kWL8-zvQig2PmSZcGPM5Zs/view?usp=sharing)
[Landing Pads](https://drive.google.com/file/d/18Selq6nd9qGv77qrFXVi943K4wO-NZRs/view?usp=sharing)

**3. The integrated circuit inside has a few different sections, but perhaps the most recognizable are the _10 cores_ where programs and instructions are run.**

[Cores](https://drive.google.com/file/d/1BK_APr5lAyoydjy5JCmgL9amR5DYAIlK/view?usp=sharing)

**4. Each core is quite complicated, so here is a diagram laying out the different functional sections. There are dozens of rather complicated elements in this diagram.**

[Diagram](https://drive.google.com/file/d/1aLkTNxuvxoK1kKEfs2RoFzu6WJ0l0pDl/view?usp=sharing)

**5. Let's zoom into a nanoscopic view of the integrated circuit so we can see indivisual transistors. These transistors are incredibly small, only a few nanometers wide and in this die there are approximately 8 to 10 billion. On top of the transistors are multiple layers of metal wires with vias rising vertically between the layers. Together these transistors and wires create a multilayer labyrinth or highway resulting in a computer that can execute billions of operations every second.**

[Outer view](https://drive.google.com/file/d/1SF5Rq0CuJxs1eqEE2nBaaN4_xqPn5tL9/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1m9He-V4UngYQIFuNJfS2WvlVZTHA5gZw/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1SpQCuSRdN_kdk-DX0TFBW1WOj8SR5hlk/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1NYTYJkCXQAiR8gCAUccfItDk0FPIdlod/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1VJByPDW28aNy_6VNZmCqrteGl4BGqhtW/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1nC8z6WkCyrxq8aYAfRLlcb-obwPSfuU4/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1xVNpfRzOENK3dFVJaz0MBnYfrSBNBbdp/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1nyyRt35GnDgmBp-RpaKOk7o645mQu6nf/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1csYWS884QyH6pF9AYPl9f6eDKuOEJXdu/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1YYv9Js0h71XzlJV8mRgHPlEvXGSYNVUj/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1Uxugu9K2UVOErGWjexYHuQBYQHufHkNr/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1uFz-ZCEnTg9R48fLSmQBa3EVjw9yFOoz/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1J17Xl2TIcuRiWKjMJRu1aeQrf_2zn9HW/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/12WuQ5H6XHzyg_YMI8mX-o3KMpKJs2ZQI/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1EGQqmSCdGMC3L9U-RSDehzKL4GAkHeeB/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1093fZ3Z1V-TkgoL2RMRR8B9HyoiKzmHF/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1iwrqk96me5l8DTLJuJkwrUg2agj8QMis/view?usp=sharing)
[Zooming......](https://drive.google.com/file/d/1gPX7zobd_RUBllLLUmD3WaeBo55MxvIz/view?usp=sharing)

**6. Let's now zoom out and look at other sections of the CPU. To the side of each core is the shared _L3 memory cache_ and ring interconnect.**

[L_3 Memory cache](https://drive.google.com/file/d/1y-1uTsAoJ1VOy1k8yrMT2djRsrD7yRz1/view?usp=sharing)
[Ring interconnect](https://drive.google.com/file/d/1gV3ZHfrRFFEk5DWkrvrc2dNGA9w51Kys/view?usp=sharing)

**7. On the far right in a intergrated graphics processor which functions as a less powerful GPU;**

[Integrated graphics processor](https://drive.google.com/file/d/18ZrE9Kzhb5oM-or36PVXdspLc1wD-TrP/view?usp=sharing)

**8. In the top left is the memory controller which sends data to and from the _DRAM_**

[Memory controller](https://drive.google.com/file/d/1pK0n3vPwEoMmNYeA0e0ZwJGVB94joXtU/view?usp=sharing)

**9. And finally on the far left is the system agent and platform _I/O_, which communicates with the chipset on the motherboard and manages the flow of data between many of the other components in our PC.**

[System agent](https://drive.google.com/file/d/1IJX-hS9spiY7OlwDda20Hk0YhPU9sHwL/view?usp=sharing)
