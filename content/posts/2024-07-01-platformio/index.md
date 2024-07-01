---
title: Selective sketch building with PlatformIO
date: 2024-07-01
---

I switched to use [PlatformIO](https://platformio.org/platformio-ide) again for tinkering with electronics and wanted to note down a quick little tip. Recently I tested some screen modules and I was looking for a way to keep different sketches around in the same project. The problem here is that by default the build process includes all `.cpp` files from the `src` directory, which is not what I want in this case. My goal was to find a way to specify a specific source file that should be used, and I found one: `build_src_filter` - https://docs.platformio.org/en/latest/projectconf/sections/env/options/build/build_src_filter.html#projectconf-build-src-filter

As an example, this is the directory tree of one of my projects:

```
.
├── include
│   └── README
├── lib
│   └── README
├── platformio.ini
├── src
│   ├── test_a
│   │   └── main.cpp
│   └── test_b
│       └── main.cpp
└── test
    └── README
```

In this case I only want to use the `main.cpp` in `test_a`, so my `platformio.ini` looks like this:

```
[env:lolin_s2_mini]
platform = espressif32
board = lolin_s2_mini
framework = arduino
lib_deps = bodmer/TFT_eSPI@^2.5.43
build_src_filter =
  +<test_a/*.cpp>
```

The last two lines are the important ones here.

