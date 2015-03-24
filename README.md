# Wunderlist::Api

TODO: Write a gem description

## Installation

Add this line to your application's Gemfile:

    gem 'wunderlist-api'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install wunderlist-api

You should require this gem like;

```
require 'wunderlist'
```

## Usage

```
# You must create API CLIENT at first.
wl = Wunderlist::API.new({
:access_token => <your access token>,
:client_id => <your client id>
})


# You can create Task
task = wl.new_task(LIST_NAME, {:title => 'Hello World', :completed => true, :due_date => '2015-03-25' })
=> #<Wunderlist::Task:0x00000000000>
task.save 

# You can delete Task
task.destroy
=> #<Wunderlist::Task:0x00000000000>
task.id
=> nil

# You can get Wunderlist::List Object
list = wl.list(LIST_NAME)
=> #<Wunderlist::List:0x00000000000>

# You can change List name
list.title = "IMOKENPI"
list.save


# You can get Wunderlist::Task Object Wrapped by Array
tasks = list.tasks
=> [#<Wunderlist::Task:0x00000000000>, #<Wunderlist::Task:0x11111111111>, ...]

or

tasks = wl.tasks([LIST_NAME1, LIST_NAME2])
=> [#<Wunderlist::Task:0x00000000000>, #<Wunderlist::Task:0x11111111111>, ...]

# You can create and update note.
note = task.note
=> #<Wunderlist::Note:0x00000000000>
note.content = "Hello World"
note.save

```

## Contributing

1. Fork it ( http://github.com/<my-github-username>/wunderlist-api/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request


# wunderlist-api

