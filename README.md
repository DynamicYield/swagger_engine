# SwaggerEngine

Include [swagger-ui](https://github.com/swagger-api/swagger-ui) as rails engine.

## Swagger specifications

https://github.com/swagger-api/swagger-spec/blob/master/versions/2.0.md

## Install

Add to Gemfile

```gem 'swagger_engine'```

Add to your config/routes.rb

```mount SwaggerEngine::Engine, at: "/api-docs"```

### Protect your route

#### Devise

```
authenticate :user do
  mount SwaggerEngine::Engine, at: "/api-docs"
end
```

or

```
authenticate :user, lambda { |u| u.admin? } do
  mount SwaggerEngine::Engine, at: "/api-docs"
end
```

## Configure

### Json files

Set the url of your json files in a initializer:

```
#config/initializers/swagger_engine.rb

SwaggerEngine.configure do |config|
  config.json_files = {
    v1: "swagger_v1.json",
    v2: "swagger_v2.json"
  }
end
```
and place them in `app/assets/javascripts/swagger_engine/`.

### Edit your json files

Use [Swagger editor](https://github.com/swagger-api/swagger-editor).

## License

This project rocks and uses MIT-LICENSE.

## Developed in collaboration with

[Rawfish](http://rawfishindustries.com)

[![Rawfish Logo](http://rawfishindustries.com/wp-content/uploads/2015/03/logo_rawfish_WEB.jpg)](http://rawfishindustries.com)
