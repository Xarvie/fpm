# fpm
A C++ header-only fixed-point math library. "fpm" stands for "fixed-point math".

[![Build Status](https://travis-ci.org/MikeLankamp/fpm.svg?branch=master)](https://travis-ci.org/MikeLankamp/fpm)
[![Build status](https://ci.appveyor.com/api/projects/status/0velpwqk38spu412?svg=true)](https://ci.appveyor.com/project/MikeLankamp/fpm)

## Why use fixed-point math?
There are several reasons why you can not or choose not to use floating-point math, but still want a similar type:
* Your target platform lacks an FPU, does not support floating-point operations or its floating-point operations are
  considerably slower than fixed-point integer operations.
* You require deterministic calculations.

If any of these reasons apply for you, and your problem domain has a clearly outlined range and required resolution,
then fixed-point numbers might be a solution for you.

## Quick Start
To use `fpm`, simply include its header `<fpm/fixed.h>` and use the `fpm::fixed_16_16`, `fpm::fixed_24_8` or `fpm::fixed_8_24`
types as if they were native floating-pointer types:
```c++
#include <fpm/fixed.h>
#include <iostream>

int main() {
    fpm::fixed_16_16 x{2.5};
    std::cout << "The cosine of 2.5 radians is: " << static_cast<float>(cos(x)) << std::endl;
    return 0;
}
```

## Documentation
Please refer to the [documentation](docs/index.md) for detailed information how to use `fpm`, its performance and its accuracy
compared to native floating pointer numbers.

## License
See the [LICENSE](LICENSE) file
