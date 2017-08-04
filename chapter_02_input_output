# Chapter 02 - Input and Output

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
