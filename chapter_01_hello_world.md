
## Chapter 01 - Hello World. 

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

### Functions and their types.

When calling a function in Haskell, we write the function's name first, followed by a space and its argument list. In the `hello world` example, `putStrLn` is the name of the function and string `"Hello, World!!"` is its argument. Therefore, `putStrLn` is a function which takes a single string as its argument. 

The type of `putStrLn` is `String -> IO ()`. This means `putStrLn` takes a String as its argument, and produces an empty value `()` wrapped in the `IO` monad. `IO` is a function that constructs a type. `IO` is a type constructor, where the empty value `()` is its argument. `IO ()` constructs the return type of `putStrLn`, or the type `putStrLn` produces. We write type annotation by writing the name first, followed by two colons, followed by its type. `putStrLn :: String -> IO ()` means that `putStrLn` is a function that takes a `String` and produces an empty value wrapped in an `IO` monad. 

### What is an `IO` Monad?

You can think of `IO` monad specifically as a real world procedure. The `()` in `IO ()` indicates that this real world procedure contains nothing inside. You can think of it as `void` in most imperative languages.  In Haskell, every function which does real world communication produces values that are wrapped in an `IO` monad. 

### What is `main`?

`main` function is the only procedure Haskell runs in the execution. It has type `IO ()`, precisely `main :: IO ()`. This makes sense because `main` is a real world procedure that talks to the console. We assigned the value produced by `putStrLn "Hello, World"` to main. `putStrLn` takes a `String` and produces a real world procedure, `IO ()`. Since we called `putStrLn` with a `String` as argument and assigned the result to `main`, the type of `main` is the same as the type of `putStrLn "Hello, World!!"`, `IO ()`.

