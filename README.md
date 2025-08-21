# Yandex::Fotki

[![Gem Version](https://badge.fury.io/rb/yandex-fotki.png)](http://badge.fury.io/rb/yandex-fotki) [![Build Status](https://travis-ci.org/huskylab/yandex-fotki.png?branch=master)](https://travis-ci.org/huskylab/yandex-fotki) [![Coverage Status](https://coveralls.io/repos/huskylab/yandex-fotki/badge.png?branch=master)](https://coveralls.io/r/huskylab/yandex-fotki?branch=master)

Ruby-клиент для работы с API http://fotki.yandex.ru/

## Установка

Добавьте в Gemfile:

```ruby
gem 'yandex-fotki'
```

или установите вручную:

```ruby
$ gem install yandex-fotki
```

## Использование

### Создание клиента

```ruby
require 'yandex-fotki'

fotki = Yandex::Fotki::Client.new(access_token: 'access_token')
```

или

```ruby
require 'yandex-fotki'

fotki = Yandex::Fotki::Client.new do |config|
  config.access_token = 'access_token'
end
```

### Получение списка альбомов

```ruby
albums = fotki.albums_get
```

### Получение альбома

```ruby
album = fotki.album_get('album_id')
```

### Получение списка фотографий в альбоме

```ruby
photos = fotki.photos_get(album_id: 'album_id')
```

### Получение фотографии

```ruby
photo = fotki.photo_get('photo_id')
```

### Загрузка фотографии

```ruby
photo = fotki.photo_post(album_id: 'album_id', file: '/path/to/file')
```

## TODO

- обработка ошибок
- создание, изменение, удаление альбомов
- изменение, удаление фотографий
- получение списка тегов
- получение списка фотографий по тегу
- получение, добавление, изменение, удаление комментариев

## Contributing

- Fork it
- Create your feature branch (git checkout -b my-new-feature)
- Commit your changes (git commit -am 'Add some feature')
- Push to the branch (git push origin my-new-feature)
- Create new Pull Request

