### rails_db
---
https://github.com/igorkasyanchuk/rails_db

```
rails '', ''
rails g rails_db initializer

rails db
runsql 'select id, name, created_at from firms limit 10'

```

```ruby
group :development do
  gem 'rails_db', '2.0.4'
end

mount RailsDb::Engine => '/rails/db', :as => 'rails_db'

config.verify_access_proc = proc { |controller| controller.current_user.admin? }

```

```
<h3>Table</h3>
<%= rails_db_data_table 'accounts',
                         footer: true,
                         columns: ['id', 'name', 'users_count'],
                         header: true,
                         style: :bootstrap %>
<h3>SQL</h3>
<%= rails_db_data_table_sql 'select id, name, age from users order by age desc limit 10',
                            footer: false,
                            header: true %>

```


