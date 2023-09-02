# stm32-usbd-no-cs

This is a patched version of
[stm32-usbd](https://github.com/stm32-rs/stm32-usbd)
which removes all of the Cortex-M critical sections.

As such, it is not interrupt safe, and the caller must ensure
that the library is never called in reentrant fashion (e.g.
by only accessing the USB driver via main-loop polling).
