# Задание 1. Разделить проект Mesto на несколько микрофронтендов

## Проектирование

Для разделения проекта на микрофронтенды был использован Webpack Module Federation, потому что весь код использует React, можно шарить общий код и использовать библиотеки для хранения глобального состояния.

## Структура и описание

Можно выделить три логические части:

- часть, ответственная за авторизацию
- часть, ответственная за работу с контентом пользователя и реакциям
- часть, ответственная за работу с профилем пользователя

Предлагается следующие 4 микрофронтенда:

- **auth** - удаленный модуль аутентификации
- **profile** - удаленный модуль для работы с профилем пользователя
- **ugc** - удаленный модуль для работы с контентом пользователя и реакциям
- **host** - основное приложение, которая загружает модули auth/profile/ugc

```
/microfrontend
  /auth
    /src
      /blocks
        /auth-form
        /login
      /components
        - InfoTooltip.js
        - Login.js
        - Register.js
      /utils
        - auth.js
  /host
    /src
      /blocks
        /content
        /footer
        /header
        /page
      /components
        - App.js
        - Footer.js
        - Header.js
        - Main.js
        - PopupWithForm.js
        - ProtectedRoutes.js
      /context
      /images
      /public
      /utils
        - api.js
      /vendor
  /profile
    /src
      /blocks
        /profile      
      /components
        - EditAvatarPopup.js
        - EditProfilePopup.js
      /utils
  /ugc
    /src
      /blocks
        /card
        /places
        /popup
      /components
        - AddPlacePopup.js
        - Card
        - ImagePopup.js
```
