# SDBM

[![Build Status](https://travis-ci.org/ruby/sdbm.svg?branch=enable-travis)](https://travis-ci.org/ruby/sdbm)

SDBM provides a simple file-based key-value store, which can only store  String keys and values.

Note that Ruby comes with the source code for SDBM, while the DBM and GDBM  standard libraries rely on external libraries and headers.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'sdbm'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install sdbm

## Usage

### Insert values:

```
require 'sdbm'

SDBM.open 'my_database' do |db|
  db['apple'] = 'fruit'
  db['pear'] = 'fruit'
  db['carrot'] = 'vegetable'
  db['tomato'] = 'vegetable'
end
```

### Bulk update:

```
require 'sdbm'

SDBM.open 'my_database' do |db|
  db.update('peach' => 'fruit', 'tomato' => 'fruit')
end
```

### Retrieve values:

```
require 'sdbm'

SDBM.open 'my_database' do |db|
  db.each do |key, value|
 puts "Key: #{key}, Value: #{value}"
  end
end
```

### Outputs:

```
Key: apple, Value: fruit
Key: pear, Value: fruit
Key: carrot, Value: vegetable
Key: peach, Value: fruit
Key: tomato, Value: fruit
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/ruby/sdbm.


## License

The gem is available as open source under the terms of the [2-Clause BSD License](https://opensource.org/licenses/BSD-2-Clause).

