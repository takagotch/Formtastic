### Formtastic
---

https://github.com/justinfrench/formtastic

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
  
  
```

```ruby
```

```

```
