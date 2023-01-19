# What is this?
This package is a one of a series packages intended to
support the development of general purpose chess engines and tools.

This package implements an engine-wrapping diluter. It works by receiving another engine's 
executable path (let's call this the underlying engine) and a probability parameter _p_. 
Everytime the engine is requested to play a move in a given position, 
it will randomly choose between:

1) (with probability _p_) forwarding the request to the underlying engine and replying back with the move chosen by it; and,
2) (with probability _1 - p_) replying with a random legal move (exactly like the [chess-random-engine](
https://github.com/leonkacowicz/chess-random-engine))

# What's the point of implementing this?

Like in the case of the [chess-random-engine](
https://github.com/leonkacowicz/chess-random-engine) this is useful to assess the 
playing ability of chess engines that are significantly weaker than modern generally
available chess engines. So one can dilute a good engine to make it less potent, and
compare it to a weaker engine.

# How do I build it?

This package uses CMake as a build-tool. In theory, it requires CMake 3.5,
but I haven't tested it with previous versions of CMake. If you manage to
build it with an older version of CMake, let me know or send a pull request
decreasing the required version on line 1 of `/CMakeLists.txt`

To build it:
```sh
mkdir build
cd build
cmake ..
make
```

# Testing
So far there are no tests implemented for this, as the implementation is trivial.
However, feel free to suggest (or send a pull request) any test cases that might
be interesting having.