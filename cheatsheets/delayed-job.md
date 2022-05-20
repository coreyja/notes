# Delayed Job

### Github Links

[https://github.com/collectiveidea/delayed\_job](https://github.com/collectiveidea/delayed\_job)

[https://github.com/collectiveidea/delayed\_job\_active\_record](https://github.com/collectiveidea/delayed\_job\_active\_record)

### Plugins

Lifecycle Hooks: [https://github.com/collectiveidea/delayed\_job/blob/master/lib/delayed/lifecycle.rb](https://github.com/collectiveidea/delayed\_job/blob/master/lib/delayed/lifecycle.rb)

```ruby
EVENTS = {
      :enqueue    => [:job],
      :execute    => [:worker],
      :loop       => [:worker],
      :perform    => [:worker, :job],
      :error      => [:worker, :job],
      :failure    => [:worker, :job],
      :invoke_job => [:job]
    }.freeze
```

