# Intro to Rails

## Week 1

* Running Ruby scripts via the CLI
* Basic input/output with puts/gets/print
* "string".inspect
* Converting strings/numbers with to_i/to_s
* "a #{input}" -> "a " + input.to_s
* rand(n)
* blocks: 5.times do, break

### Extensions

* What if you entered in an empty input, or an input outside of 1..10?

### Questions

* How do you quickly indent blocks in your favourite text editor?

## Week 1.1

* Duck types (strings, arrays)
* String#split
* gets returning \n, String#chomp
* Hashes with "keys" and :keys => and keys: 
* irb
* Classes, Class.new, initialize, methods through def
* Class.new(args)
* Class instance variables with @var
* instance.instance_variable_get("@var")
* load 'filename.rb' in irb
* Implicit return
* Extending classes with the same name: two classes in the same file
* `a.b = c` -> `a.b=(c)`
* `def var=(a)`
* attr_reader, attr_writer, attr_accessor
* `array.push(e)` vs `array << e`
* `array.shuffle()` vs `array.shuffle!()`
* Array.detect {block}
* blocks with {} or do..end
* `foo.each { |a| a.bar }` === `foo.each(&:bar)`
* Inheritance
* Modules as namespaces, ModuleName::Class

### Extensions

* Look at array destructuring `a, b = [1, 2]`
* Why are number/symbol accesses to a Hash faster than using a String in Ruby?

### Questions

* Difference between hash("string" => ...) and hash(:string => ...)?
* What does a 'key' mean in a Hash?
* Why does `puts "#{array}"` print differently from `puts array`?
* What is the difference between an Object and a Hash?
* Why does irb show different results from puts for an object?
* What are vaild Ruby method names?
* How do you comment out a block in your favourite IDE?

May need some extra Ruby training for effective understanding of the language, e.g. the courses very quickly goes over scopes, variables, classes, types, symbols, methods, return values, implicit return, getter/setter methods, method ownership, class inheritance, modules/namespaces

Maybe have a break after 57 minutes.

## Week 2

* Rails controllers/models/views
* What ALL the Rails folders and subfolders do
* Should put business logic within models, rather than controllers
* Gemfile, major/minor/patch versioning
* Co-ordinating databases with migrations
* Creating migrations manually
* Migration.up/down vs Migration.change
* All model classes are singular
* `rails console` c.f. `irb`
* ActiveRecord::Base#attr_accessible
* Model.all
* model.save, model.update_attributes, model.destroy
* `rails server` (`rails s`)
* Views, templates
* Model/index, show, new, create
* `rake routes`
* `reload!` in `rails console`
* Routes with `get`, `post`, `put` (`patch` in Rails 4)

### Extensions

* You should consider initialising a Git repository immediately after `rails create` so you can track your changes.
* Consider adding .editorconfig immediately to your Rails project
* Look at how to create tables with `rails generate` directly rather than editing migration files
* Do not try to create all database columns immediately, but only when necessary

### Questions

* What is "precompilation" in terms of Rails?
* When would you put something in vendor/assets/javascripts?
* Why does state not persist across web requests?

Is it OK to be using Rails 4.1.5 rather than 3.2.11? You will need to mark params as required: http://stackoverflow.com/questions/17335329/activemodelforbiddenattributeserror-when-creating-new-user

It might be helpful to have some diagrams to show how the web browser/controller/view/models etc work together, rather than just talking.

May need extra web concepts training: goes very quickly over web requests, states, schemas, database column types, database columns, primary keys, "index" action, HTML elements/forms/inputs/IDs, HTTP GET/POST

## Week 3

* CRUD
* `resources :model` in routes.rb
* Path helpers
* `link_to`, `redirect_to` -> `app.polymorphic_path`
* `rails generate model`, `column:belongs_to`
* ActiveRecord#belongs_to, ActiveRecord#has_many
* `Model.childrens << Children.new()` ~= `Model.childrens.new().save()`
* `polymorphic_path([Child.first.parent, Child.first])`

Question: Why is there not a `delete_deck_path` helper?

## Week 4

* `form_for [@parent, @child]`
* _partials
* Cookies, `cookies.signed`
* Controllers without models
* root paths
* `helper_method`
* Falsiness of `nil`
* `0` is true in Ruby
* views/layouts/application.html.erb

Does not cover implicit return returning nil if there are no returns
