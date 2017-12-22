editor: https://pastebin.com/mt2EXpfy

# my_store 新增 User, Store

- User 1:1 Store N:N Product

```
$ rails g model User name email tel
$ rails g model Store title address tel user:references
$ rails g model Product name price:integer available:boolean store:references
$ rails g model WareHouse store:references product:references

$ rails g db:migrate
```


# 新增User, Store, Product

- Store 指定給 User

```
$ rails console

> u1 = User.new(name: "S1")
> u1.save

> s1 = Store.new(...)
> u1.store = s1

> u2 = User.second
> u2.build_store(...)
> u2.save

> u2.create_store(...)

> s1 = Store.first
> p1 = Product.new(...)
> p2 = Product.new(...)
> s1.products = [p1, p2]
```

# 美化介面 = "Hirb-unicode"

- in Gemfile:
```
gem 'hirb-unicode'

$ bundle install

$ rails c
> Hirb.enable
```
