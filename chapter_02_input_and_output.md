# Chapter 02 - Input and Output and ghci

```file: ch02.hs```
```haskell
main :: IO ()
main = do
    putStrLn "What's your name?"
    name <- getLine
    putStrLn ("Hello, " ++ name ++ "!!")
```

## `do` Notation

The `do` notation is used to chain together multiple actions into a single action. Every statement under `do` that is indented the same level is considered the body of the do statement. 

## `getLine`

`getLine` is of type `IO String`. This means a real world procedure that contains a `String` inside it. We use left arrow, `<-` to unwrap the IO monad and get the string inside, so the type of `name` is `String`. We use `++` to concatenate strings together. 

## `ghci` Interpreter

`ghci` is the haskell REPL interpreter. It is useful to quickly check whether we have written the correct code, even if we did not write the `main` function. Give it a try on the terminal:

```
$ ghci ch02.hs
GHCi, version 8.0.2: http://www.haskell.org/ghc/  :? for help
[1 of 1] Compiling Main             ( ch02.hs, interpreted )
Ok, modules loaded: Main.
*Main> 
```

Type `main` to call main function.

```
*Main> main
What's your name?
Haskell
Hello, Haskell!!
*Main> 
```

## Check the type using `:type`

We can check the type of various pieces of function on `ghci` using command `:type` or `:t`. 

```
*Main> :type main
main :: IO ()
*Main> :t getLine
getLine :: IO String
*Main> :t putStrLn
putStrLn :: String -> IO ()
*Main> 
```

## Some useful arithmetics

We can evaluate simple mathematical expressions on ghci. All mathematical expressions are valid functions in haskell.

```
*Main> 3 + 2
5
*Main> 4 * 5
20
*Main> 2 ^ 3
8
*Main> 4 / 2
2.0
*Main> 
```

## Boolean Types and Equality Comparison

```
*Main> 3 == 2
False
*Main> 2 == 2
True
*Main> True == True
True
*Main> True && False
False
*Main> False || True
True
*Main> 3 /= 2
True
*Main> 
```

Haskell uses `/=` to compare inequality. 


