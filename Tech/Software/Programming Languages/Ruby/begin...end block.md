---
aliases: block
created: 2021-12-20, 1:57:27 pm (Monday, December 20th)
updated: 2021-12-20, 3:27:57 pm (Monday, December 20th)
---
#ruby

# begin...end blocks
`begin...end` can be used to encapsulate multiple lines of code that will may be stored in a variable

## Context
I first saw this in Ivan's constraint solver.

```ruby
# Replaced contextual names with less meaningful names
def constraint_by_day
  @_constraint_by_day ||=
    begin
      constraints = Constraint.constraints(x)

      h = constraints.index_by(&:day)
      h.default_proc = proc do |hash, day|
        hash[day] = Constraint.other_constraint(day)
      end
      h
    end
end
```

## Related
Looked up docs on this alongside:
- [[Tech/Software/Programming Languages/Ruby/attr accessor reader writer]]
- [[Tech/Software/Programming Languages/Ruby/Hash]]
- [[Tech/Software/Programming Languages/Ruby/private attributes]]