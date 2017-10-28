# Exercises

#### Mood Swing

`data Mood = Blah | Woot deriving Show`

1. Type constructor: `Mood`

2. Data constructors: `Blah` and `Woot`

3. `changeMood :: Mood -> Woot` - This is not ideal because it does not support changing mood back to `Blah`

4. ```haskell
   changeMood Blah = Woot
   changeMood _ = Blah -- catchall
   ```

