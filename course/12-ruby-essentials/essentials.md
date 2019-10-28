## Variables in Ruby
```
Variables are the memory locations, which hold any data to be used by any program.
```

Syntax:
```
<variable_name> = <value>
```

Example:
```
employee_name = 'Partha'
employee_id = 001
is_contactor = true
old_employee = false
on_site_experience = nil
```

## String formatting
```
puts "#{employee_name}"
```


## Comments
- Single line comment
```
# This is a comment
```

- MultiLine comment
```
=begin
Some statement
=end
```

## Skeleton
`helloworld.rb`
```
puts 'hello-world'
```

## Arrays
Array is used to store set of elements with a single reference

- Defining an array
Example:
```
products = ['1', '2', 3]
```

- Accessing array elements
Example:
```
puts products[0]
```

- Iterating through an array
Example:
```
products.each do |product|
    puts "#{product}"
end
```

## Hashes
Hash is used to store key, value pair and valuee can be accessed by using keys.

- Defining hash
Example:
```
employee = {
    "name" => "Partha",
    "designation" => "Software Engineer"
}
```

- Accessing values
Example:
```
employee['name']
# Printing value
puts employee['name']
```

- Iterating through hash
Example:
```
employee.each do |key, value|
    puts "Key: #{key} => #{value}"
    if value.class == Hash
        puts "Keys: #{value.keys}"
    end
end
```

## Methods
Ruby methods are very similar to functions in any other programming language. Ruby methods are used to bundle one or more repeatable statements into a single unit.

- Defining a method
Example:
```
def run
    puts "this is run method"
end
```

- Calling a method
Example:
```
run
```
Or
```
run()
```

## Blocks

You have seen how Ruby defines methods where you can put number of statements and then you call that method. Similarly, Ruby has a concept of Block.

A block consists of chunks of code.

You assign a name to a block.

The code in the block is always enclosed within braces ({}).

A block is always invoked from a function with the same name as that of the block. This means that if you have a block with the name test, then you use the function test to invoke this block.

You invoke a block by using the yield statement.

Example:
```
#!/usr/bin/ruby
# Method
def test
   puts "I'm from test method"
end

# Block
test {
    puts "I'm from block"
}
```

Another Example:
```
#!/usr/bin/ruby
# Method
def test
   puts "Working on step - 1"
   yield 1
   puts "Working on step - 2"
   yield 2
end

# Block
test {
    |i| puts "step - #{i} completed"
}
```

