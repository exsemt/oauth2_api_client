# oauth2_api_client

[![Build Status](https://secure.travis-ci.org/mrkamel/oauth2_api_client.svg?branch=master)](http://travis-ci.org/mrkamel/oauth2_api_client)
[![Gem Version](https://badge.fury.io/rb/oauth2_api_client.svg)](http://badge.fury.io/rb/oauth2_api_client)

Oauth2ApiClient is small, but powerful client around
[oauth2](https://github.com/oauth-xx/oauth2) and
[http-rb](https://github.com/httprb/http) to interact with APIs which use
oauth2 for authentication with automatic token caching and renewal.

```ruby
client = Oauth2ApiClient.new(
  base_url: "https://api.example.com/",
  client_id: "the client id",
  client_secret: "the client secret",
  oauth_token_url: "https://auth.example.com/oauth2/token",
  max_token_ttl: 3600, # optional
  cache: Rails.cache # optional
)

client.post("/orders", json: { address: "..." }).status.success?
client.headers("User-Agent" => "API Client").timeout(read: 5, write: 5).get("/orders").parse
# ...
```

## Install

Add this line to your application's Gemfile:

```ruby
gem 'oauth2_api_client'
```

and then execute

```
$ bundle
```

or install it via

```
$ gem install oauth2_api_client
```

## Semantic Versioning

Oauth2ApiClient is using Semantic Versioning: [SemVer](http://semver.org/)

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
