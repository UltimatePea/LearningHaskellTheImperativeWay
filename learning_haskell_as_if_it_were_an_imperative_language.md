# Learning Haskell the Imperative Way

Haskell is known as a purely functional programming language. However, thanks to the `do` syntax sugar on monads, it can be viewed from an imperative perspective. Opposed to traditional tutorials, this tutorial aims to migrate the concepts from imperative perspective to Haskell’s pure functional concepts. It starts with the IO Monad and introduces functional programming concepts as time progresses. Your feedback of this tutorial is extremely important. Please submit any feedbacks through [Issues Page]( https://github.com/UltimatePea/Blog/issues) or email me at zhc159@ucsd.edu.  

## Prerequisite

### Knowledge

This tutorial assumes that the reader knows most language features of the Java programming language.

### Installation

Please install [The Haskell Platform](https://www.haskell.org/platform). This tutorial gives syntax to compile the program under macOS. 

## Hello World. 

We will begin with the typical `Hello, World` routine that is found on most imperative programming languages.

`File: helloworld.hs`
```haskell
main = putStrLn "Hello, World!!"
```

Save the above file as `helloworld.hs` and run the program using `runhaskell`.

```
$ runhaskell helloworld.hs
Hello, World!!
$
```

## Hello World Explained

### Functions and its types.

When calling a function in Haskell, we write the function's name first, followed by a space and its argument list. In the `hello world` example, `putStrLn` is the name of the function and string `"Hello, World!!"` is its argument. Therefore, `putStrLn` is a function which takes a single string as its argument. 

The type of `putStrLn` is `String -> IO ()`. This means `putStrLn` takes a String as its argument, and returns an empty value `()` wrapped in the `IO` monad. `IO` is a function that constructs a type, namely a type constructor, where the empty value `()` is its argument. `IO ()` constructs the return type of `putStrLn`. We write type annotation by writing the name first, followed by two colons, followed by its type. `putStrLn :: String -> IO ()` means that `putStrLn` is a function that takes a String and returns an empty value wrapped in an `IO` monad. 

### What is a Monad?

You can think of monad as a box. `IO` monad is a box which exposes real world communication such as console interaction to the program itself. In Haskell, every function which does real world communication has to be wrapped in an `IO` monad. Please read on if you don't understand the monad concept. For the time being, you can think of it as a compiler type hint. 

### What is `main`?

`main` function is the only function Haskell runs in the execution. It has type `IO ()`. This makes sense because `main` is something that talks to the realworld. We assigned the value of `putStrLn "Hello, World"` to main. `putStrLn` takes a `String` and returns `IO ()`. Since we called `putStrLn` with a `String` as argument and assigned the result to `main`, the type of `main` is the same as the type of `putStrLn "Hello, World!!"`, `IO ()`.

