Compiling
=========

`dune build` should be enough to compile chamelon, with the OCaml 4.14 compiler.


Usage
=====

Basic usage is:
`chamelon -c "[compile command]" input.ml`

This will execute the compilation command on `input.ml`, and produce an output `input_min.ml`
where the compilation command still raises `Misc.Fatal_error`.

The following options are also available:
- `-e [error]`: this looks for `[error]` in the output of the compilation command instead
  of `Misc.Fatal_error`.
- `-o [file]`: this will use `[file]` as the ouput instead of the default, suffixing the
  input file with `_min`. Inplace minimization can be achieved by setting the output file
  to the input file.
- `-t [command]`: this uses `[command] input.ml` to produce a `.cmt` file, instead of using the
  compilation command. This is useful if you want to minimize a file when the compilation command
  produces `.cmt` files incompatible with the version of OCaml chamelon is compiled with.
- `-m [minimizers]`: this runs the minimizers from the comma-separated list of minimizers given
  as arguments instead of the default iteration order.