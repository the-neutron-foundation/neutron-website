Sandboxes
=========
---

Sandboxes allow you to play around with neutron without affecting any of the
variables in the main neutron program. They are just code inside a `sandbox`
code block. Example:

```neutron
sandbox {
  import "io";
  x = 20;
  io::print(x);
}
// Outside variables aren't affected
// x isn't defined
// io also isn't defined
```
