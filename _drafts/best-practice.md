## Put search on moden not controller
ex: 
```ruby
def self.search(query)
    return all unless query.present?
    query = "%#{query.strip.downcase}%"
    where('lower(first_name) LIKE :search OR
          lower(last_name) LIKE :search OR
          lower(name) LIKE :search OR
          lower(email) LIKE :search', search: query)
end
```

## always use i18n instead of hard coded text

## user `as_json`
In rails use `as_json` instead `to_json` to convert into json formate
`to_json` return `string` where `as_json` return `hash`

##
