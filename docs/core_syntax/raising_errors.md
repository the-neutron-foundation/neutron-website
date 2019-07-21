Raising Errors
==============
---

To raise errors in Neutron, you must create an instance of the built-in `error`
class, and run the `raise` function on the class. Example:

```neutron
error("bad_error")::raise("Something Went Wrong", ln=10, file="path_to_file_where_error_occured");
```

You can also raise errors using embedded python code. Example:

```neutron
`errors.ErrorClass("bad_error").raise_error(
  "Something Went Wrong",
  ln=10,
  file="path_to_file_where_error_occured")`;
```

It is recommended to use the Neutron variant of raising error because
it is more supported.
