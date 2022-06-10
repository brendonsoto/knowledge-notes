---
aliases: 
created: 2022-05-19, 2:07:41 pm (Thursday, May 19th)
updated: 2022-05-23, 10:18:58 am (Friday, May 20th)
---
## Create a test
`bin/rails g rspec:request <name-of-request>`
*Note:* make sure you pass in the *request name* **not** the controller name

According to the RSpec team, `controller` tests are obsolete, hence `request`
Sources:
- https://medium.com/just-tech/rspec-controller-or-request-specs-d93ef563ef11
- https://stackoverflow.com/questions/40851705/controller-specs-vs-request-specs

## Run a single test file
`bin/rake rspec SPEC=path/to/spec.rb`

## Run a single test from a file
`bin/rake spec SPEC=path/to/spec.rb -e \"<Name of test or block of tests>\"`
OR
`rspec file_name:test_line_#`

## Run all tests
`bin/rake rspec`
