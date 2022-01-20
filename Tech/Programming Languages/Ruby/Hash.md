---
aliases: dictionary associative-array
created: 2021-12-20, 1:46:02 pm (Monday, December 20th)
updated: 2021-12-20, 1:53:40 pm (Monday, December 20th)
---
#ruby

# Hash
[source](https://ruby-doc.org/core-2.7.0/Hash.html)

## Using `.new`
When given a block, accessing the hash will go through the code in the block to return a value.

## Contextual example
I first came across this from Ivan's constraint solver and was confused.

```ruby
def minimum_bound_by_day
  @_minimum_bound_by_day ||=
    Hash.new do |hash, day|
      curr = merchant_constraint(day)
      prev = merchant_constraint(day.add_days(-1))
      hash[day] = curr.minimum_bound(prev)
    end
end
```

It was used like so:

```ruby
def minimum_bound(day)
  minimum_bound_by_day[day]
end
```

I was confused because I did not see any function argument in `minimum_bound_by_day`.

I now see that when calling `minimum_bound_by_day[day]` what's happening is whatever `day` is is being passed into the block provided to `Hash.new`