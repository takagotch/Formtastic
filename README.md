### Formtastic
---

https://github.com/justinfrench/formtastic

```sh
gem 'formtastic', '~> 3.0'
rails g formtastic:install

rails g formtastic:input string --extend
rails g formtastic:input string --extend

```

```html
<%= sematic_form_for @article do |f| %>
  <%= f.input :name :title => "Basic" do %>
  <%= f.input :body %>
  <%= f.input :section %>
  <%= f.input :publication_state, :as => :radio %>
  <%= f.input :category %>
  <%= f.input :allow_comments, :label => "Allow commenting on this article" %>
<% end %>  
<%= f.inputs :name => "Advanced" do %>
  <%= f.input :keywords, :required => false, :hint => "Example: ruby, rails, forms" %>
  <%= f.input :extract, :required => false %>
  <%= f.input :description, :required => false %>
  <%= f.input :url_title, :required => false %>
<% end %>
<% f.inputs :name => "Author", :for => :author do |author_form| %>
  <%= author_form.input :first_name %>
  <%= author_form.input :last_name %>
<% end %>
<%= f.actions do %>
  <%= f.action :submit, :as => :button %>
  <%= f.action :cancel, :as => :link %>
<% end %>
<% end %>  

# app/assets/stylesheets/application.html.erb
<%= stylesheet_link_tag 'application' %>
  
<%= semantic_form_for @user do |f| %>
  <%= f.inputs %>
  <%= f.actoins %>
<% end %>  
  
<%= semantic_form_for @user do |f| %>
  <%= f.inputs :title, :body, :section, :categories, :created_at %>
  <%= f.actions :submit, :cancel %>
<% end %>
  
<%= semantic_form_for @post do |f| %>
  <%= f.inputs do %>
    <%= f.input :title %>
    <%= f.input :body %>
    <%= f.input :section, :as => :radio %>
    <%= f.input :categories %>
    <%= f.input :created_at, :as => :string %>
  <% end %>
  <%= f.actions do %>
    <%= f.action :submit, :as => :button %>
    <%= f.action :cancel, :as => :link %>
  <% end %>
<% end %>
  
<%= semantic_form_for @post do |f| %>
  <%= f.inputs "Basic", :id => "basic" do %>
    <%= f.input :title %>
    <%= f.input :body %>
  <% end %>
  <%= f.inputs :name => "Advanced Options", :id => "advance" do %>
    <%= f.input :slug, :label => "URL Title", :hint => "Created automatically if left blank", :required => false %>
    <%= f.input :section, :as => :radio %>
    <%= f.input :user, :label => "Author" %>
    <%= f.input :categories, :required => false %>
    <%= f.input :created_at, :as => :string, :label => "Publication Date", :required => false %>
  <% end %>
  <%= f.actions do %>
    <%= f.action :submit %>
  <% end %>
<% end %>
  
<%= semantic_form_for [@author, @post] do |f| %>
  
<%= semantic_form_for @post do |f| %>
  <%= f.inputs :title, :body, :created_at %>
  <%= f.semantic_fields_for :author do |author| %>
    <%= author.inputs :first_name, :last_name, :name => "Author" %>
  <% end %>
  <%= f.actions %>
<% end %>
  
<%= semantic_form_for @post do |f| %>
  <%= semantic_form_for @post do |f| %>
  <%= f.inputs :name => 'Category #%i', :for => :categories %>
  <%= f.actions %>
<% end %>
  
<%= semantic_form @post do |f| %>
  <%= f.inputs :for => :categories do |category, i| %>
  <%= f.actions %>
<% end %>
  
<%= semantic_form_for(@post, :namespace => 'cat_form') do |f| %>
  <%= f.inputs do %>
    <%= f.input :title %>
    <%= f.input :body %>
    <%= f.input :created_at %>
  <% end %>
  <%= f.actions %>
<% end %>
  
<%= semantic_form_for @post do |f| %>
  <%= f.inputs do %>
    <%= f.input :title, :input_html => { :size => 10 } %>
    <%= f.input :body, :input_html => { :class => 'autogrow', :rows => 10, :cols => 20, :maxlength => 10 } %>
    <%= f.input :created_at, :input_html => { :disabled => true } %>
    <%= f.input :updated_at, :input_html => { :readonly => true } %>
  <% end %>
  <%= f.actions %>
<% end %>
  
<%= semantic_form_for @post do |f| %>
  <%= f.actions do %>
    <%= f.action :submit, :button_html => { :class => "primary", :disable_with => 'Wait...' } %>
  <% end %>
<% end %>
  
<%= semantic_form_for do |f| %>
  <%= f.inputs do %>
    <%= f.input :title, :wrapper_html => { :class => "important" } %>
    <%= f.input :body %>
    <%= f.input :description, :wrapper_html => { :style => "display:none;" }%>
  <% end %>
<% end %>

  
  
<%= semantic_form_for @post do |f| %>
  <%= f.semantic_errors :state %>
<% end %>
  
  
<%= semantic_form_for @post do |f| %>  
  <%= f.inputs do %>
    <%= f.input :title %>
    <%= f.input :body %>
    <%= f.input :section %>
  <% end %>
<% end %>
  
Formatastic::FormBuilder.i18n_lookups_by_default = true
  
<%= semantic_form_for Post.new do |f| %>
  <%= f.inputs do %>
    <%= f.input :title %>
    <%= f.input :body %>
    <%= f.input :section %>
  <% end %>
  <%= f.action do %>
    <%= f.action :submit %>
  <% end %>
<% end %>
  
<%= semantic_form_for @post do |f| %>
  <%= f.inputs.:post_details do %>
  <% end %>
<% end %>
  
<%= semantic_form @post do |f| %>
  <%= f.inputs do %>
    <%= f.input :title %>
    <%= f.input :body, :hint => false %>
    <%= f.input :section, :label => 'Some section' %>
  <% end %>
  <%= f.actions do %>
    <%= f.action :submit, :label => :dumie %>
  <% end %>
<% end %>
  
<%= semantic_form_for @post do |f| %>  
  <%= f.inputs do %>
    <%= f.input :title, :label => true %>
    <%= f.input :body, :label => true %>
    <%= f.input :section, :label => true %>
  <% end %>
  <%= f.actions do %>
    <%= f.action :submit, :label => true %>
  <% end %>
<% end %>  
  
<%= semantic_form @post do |f| %>
  <%= f.inputs do %>
    <%= f.input :title, :label => true %>
    <%= f.input :body, :label => true %>
    <%= f.input :section, :label => true %>
  <% end %>
  <%= f.actions do %>
    <%= f.action :submit, :label => true%>
  <% end %>
<% end %>
  
<%= semantic_form_for @post do |f| %>
  <%= f.semantic_errors :state %>
<% end %>
```

```ruby
# config/environments/production.rb
config.assets.precompile += %w( ie6.css ie7.css )


Formtastic::FormBuilder.i18n_lookups_by_default = false

class StringInput < Formtastic::Inputs::StringInput
  def to_html
    puts "this is my modified version of StringInput"
    super
  end
end

f.input :authors, :as => :check_boxes, :collection => User.order().all
f.input :authors, :as => :check_boxes, :collection => current_user.company.users.activate
f.input :authors, :as => :check_boxes, :collection => [@justin, @kate]
f.input :authors, :as => :check_boxes, :collection => ["Justin", "Kate", "Amelia", "Gus", "Meg"]
f.input :author, :as => :check_boxes, :collection => Author.all
f.input :author, :as => :select, :collection => Author.pluck(:first_name, :id)
f.input :author, :as => :select, :collection => Author.pluck(Arel.sql("CONCAT(`first_name`, ' ', `last_name`)"), :id)
f.input :author, :as => :select, :collection => Author.your_custom_scope_or_class_method
f.input :author, :as => :select, :collection => { @justin.name => @justin.id, @kate.name => @kate.id }
f.input :author, :as => :select, :collection => ["Justin", "Kate", "Amelia", "Gus", "Meg"]
f.input :author, :as => :radio, :collection => User.all
f.input :author, :as => :radio, :collection => [@justin, @kate]
f.input :author, :as => :radio, :collection => { @justin.name => @justin.id, @kate.name => @kate.id }
f.input :author, :as => :radio, :collection => { @justin.name => @justin.id, @kate.name => @kate.id }
f.input :author, :as => :radio, :collection => ["Justin", "Kate", "Amelia", "Gus", "Meg"]
f.input :author, :as => :radio, :collection => ["Yes!", "No"]
f.input :author, :as => :radio, :collection => Hash[Book.all.map {|b| [b.name,b.id]}]
f.input :author, :as => :datalist, :collection => Book.pluck(:name)

Formtastic::FormBuilder.i18n_lookups_by_default = false

class String Input < Formtastic::Inputs::StringInput
  def to_html
    puts "this is my modified version of StringInput"
    super
  end
end

class FlexibleTextInput < Formastic::Inputs::StringInput
  def input_html_options
    super.merge(:class => "flexible-text-area")
  end
end

class DatePickerInput
  include Formtastic::Inputs::Base
  def to_html
  end
end

```

```css
# app/assets/stylesheets/application.css
*= require formtastic
*= require my_formtastic_changes

```

```yml
en:
  formstatic:
    labels:
      title: "Title"
      article:
        body: "Article content"
      post:
        new:
          title: "Choose a title..."
          body: "Write something..."
        edit:
          title: "Edit title"
          body: "Edit body"

en:
  formtastic:
    titles:
      post_details: "Post details"
    labels:
      post:
        tilte: "Your Title"
        body: "Write something..."
        edit:
          title: "Edit title"
    hints:
      post:
        title: "Choose a good title for your post."
        body: "Write something inspiring here."
    placeholders:
      post:
        title: "Title your post"
        slug: "Leave blank for an automatically generated slug"
      user:
        create: "Create my %{model}"
        update: "Save changes"
        reset: "Reset form"
        cancel: "Cancel and go back"
        dumie: "Launch!"
  
en:
  formtastic:
    labels:
      title: "Title"
      article:
        body: "Article content"
      post:
        new:
          title: "Choose a title..."
          body: "Write something..."
        edit:
          title: "Edit title"
          body: "Edit body"
          
```

