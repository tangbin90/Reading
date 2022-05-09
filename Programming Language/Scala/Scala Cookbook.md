
```scala
for (i <- Array(1,2,3)) println(i)
```

## REPL
REPL—Scala’s Read/Eval/Print/Loop—by typing scala at your operating system command line.
``` Scala
// Get varaiables type
:type x
x.getClass
```
use REPL in sbt
```scala
MyProject> console
scala>
```

```scala
// for/yield
scala> **`for (i <- Array(1,2,3)) yield i * 2`**
res0: Array[Int] = Array(2, 4, 6)

// map
scala> **`Array(1,2,3).map(_ * 2)`**
res1: Array[Int] = Array(2, 4, 6)

scala> val nums = List(1,2,3,4,5).filter(_ < 4)
nums: List[Int] = List(1, 2, 3)
```
'_' is a placeholder for each element in the collection.

## String
when you precede your string with the letter s, you’re creating a processed string literal.
```scala
val s = "eggs, milk, butter, Coco Puffs"`

s.split(",").map(_.trim)

"hello world, this is Al".split("\\s+")

//substitution
val name = "Fred"
println(s"$name is $age years old, and weighs $weight pounds.")
//Any arbitrary expression can be embedded in ${}
println(s"Age next year: ${age + 1}")
println(s"${hannah.name} has a score of ${hannah.score}")
```

The f string interpolator (printf style formatting)
```scala
scala> println(f"$name is $age years old, and weighs $weight%.0f pounds.")
```
