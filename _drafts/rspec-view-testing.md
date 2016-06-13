## Passing instance object to view
Using `assign` method we can pass required instance object to view
ex:

```ruby
assign(:company, company)
```
in above code we assign view's `@company` with company

## Allow `current_user` in veiw test
```ruby
allow(view).to receive(:current_user).and_return(user)
```
now we can test view that need devise `current_user` where `current_user` will return `user` object

`allow(Foo).to receive(:bar).with(baz).and_return(foobar_result)`
In above code `:bar` is method `:baz` is parameter 
So, we can pass paramete using `with` during method stubing

