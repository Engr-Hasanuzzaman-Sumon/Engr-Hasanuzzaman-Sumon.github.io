#four best practices:

## It describes a set of expectations

## Each example (a line beginning with it ) only expects one thing
for example test firstname , lastname , and email validations separately

## Each example is explicit
Though description of it is optional but It will be hard to read if we ommit it.

## Each example’s description begins with a verb, not should
```ruby
describe Contact do
it "is valid with a firstname, lastname and email"
it "is invalid without a firstname"
it "is invalid without a lastname"
it "is invalid without an email address"
it "is invalid with a duplicate email address"
it "returns a contact's full name as a string"
end
```ruby

We will pass test value through `expect()` method, then chains a matcher to it:
N.b: We can use either `to` or `not_to` with  `expect()` method

