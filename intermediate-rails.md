# Intermediate Rails

## Week 1

* Strong parameters
* Using the `monban` gem and generators for simple user registration/authentication
* ApplicationController#before_filter
* routes.rb: `resource` vs `resources`, when to use [:only] verbs
* `<%= render @object %>`
* `div_for object` for <div> styling
* `time_ago_in_words`
* `default_scope` for default sorting models DESC
* Model validation with Model#validates(presence: true)
* `object.save` returns true or false based on validation
* Flash variables accessible in application layout

Question: Does your favourite IDE support automatic intending?
Question: Is there an inline `div_for`?

Using Rails 4 is going to be quite complicated without experience. Rails --without doesn't work in 4.
* Don't use strong_parameters gem
* Add the `monban-generators` gem in Rails 4
* However the talk does mention which parts can be ignored in Rails 4 apps

Goes very quickly through Rails concepts, encourages blind typing without thinking.
Very quickly goes over flash variables with zero discussion.

## Week 2

* Encouraging resource-ful actions only in controllers
* Single-table inheritance (STI), uses nil values
* "Polymorphism" being multiple-table
* Editing migrations directly after generate but before migration
* Composite indexes
* Transactions in a tree of saving children to prevent orphans
* Polymorphic classes with `belongs_to: ..., polymorphic: true`
* Using the `paperclip` gem for image uploads
* `db/schema.rb`
* Gravatars, Digest::MD5, `require`
* Helpers modules
* Optional method arguments in Ruby: `def foo(bar = 123)`
* get, post children routes
* `has_many :assocations, through: :other, class_name: 'NotAssociation'`

Question: Why [content_id, content_type] and not [text_id = nil, photo_id = nil]? When would one be better than the other?
Question: Are there better column names than follower_id and followed_user_id?

Probably need more discussion on database inheritance approaches, on composite indexes, on association tables

Don't use Windows!

## Week 3

* Moving business logic from controller to model
* Cheap caching local values with `@_user ||= ...`
* Unnecessary abstraction with moar objects
* "SOLID" principles
* "Service objects" that aren't ActiveRecord models
* `to_partial_path` so a service object can be <%= render obj %>
* Model.where(id: [1, 2, 3]) -> WHERE id IN ...
* Concerns through `include ConcernName...` in app/models/concerns/concern_name.rb

Question: When do Ruby query caches apply? Can you have stale data?
Question: When would using your own cheap cache be a bad idea? What if you wanted to invalidate the cache?
Question: Why would moving Following to a Concern be a bad idea? (We only use the concern once!)

A bit of premature optimisation, but that's OK.
I don't agree with creating a "Dashboard" object yet, since the Dashboard object doesn't have anything unique other than collations...
I DON'T agree with following hipster design patterns based on what cool people are saying in Internet videos. Concepts such as "single responsibility" and "open close" is fine but you need to have the experience of when to use/not use it and why. c.f. GoF book. I would suggest rather having a good study on design patterns based on the GoF book rather than following a random video.
Not sure why we have a Timeline object, we could have just had it in Dashboard.timeline
"Hard to paginate" but we haven't talked about pagination yet

`extend ActiveModel::Naming` doesn't seem to work in Rails 4, you still have to have `to_partial_path`.

## Week 4

* Coding styles; "coding is an emotional response"
* String#gsub, $1 global variable, String#[1..-1]
* strip_tags(), String#html_safe
* Subselects
* Class methods: def self.foo()
* Hash#fetch(key, default)
* Class#after_create, #after_update
* `rails-observers` gem for after_save
* ruby-toolbox.com for comparing/searching gems
* `rake -T` to list all rake tasks
* Using `sunspot` gem to implement `searchable` indices
* Model#reindex to reindex solr objects
* ActiveRecord doesn't support Views

Question: When would be the best times to commit our changes to the codebase?
Question: Is the problem of searching both content_types is because of using [content_id, content_type] rather than [text_id, photo_id]?

Should discuss what class and instance methods are!
