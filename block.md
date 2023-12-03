Block is a snippet of code that can be passed through methods.
Method can pass value optionally anticipating a block so that
block can make use of that value to write code around it.

Closures are function objects that remember the 'context' in
which they were created. For eg.-

```
def proc_test
  some_var = 9
  Proc.new{|x| x+some_var}
end
```

Now when `proc_test` is called it returns an object which returns
an object. The object remembers the value of `some_var` from the
method. Object might look like: <object x+9>

Procs are blocks that can be stored in variable. It remembers the
context in which it is created. follows closure property.

Ways to yield

```
def bla
  some_operation
  yield valuable_result
  some_operation
end
```

Valuable result can accessed by passing block `bla {|val_result| ..}`

```
def bla(&block)
  some_operation
  block.call(valuable_result)
  some_operation
end
```

The above method wants a block to be passed as argument. If block isnt
passed it will throw error. Block here is an proc object, we know this
because `&` is used before the parameter. & converts block to proc 
object.So, we can use `block.call`. passing block is optional.


```
def bla(proc_var)
  some_operation
  proc_var.call(valuable_result)
  some_operation
end
```

`proc_var = Proc.new{|val_result| someoperationwithval_result}`
Now we can pass the variable directly `bla(proc_var)`
