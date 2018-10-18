# "Becoming a Multilingual Superhero in Django" by Sanyam Khurana

## Getting started

* Install the `LocaleMiddleware` in `MIDDLEWARES`
* Define list of languages
* `USE_I18N = True`
* `USE_L10N = True`
* Set a default language
* Define `LOCALE_PATHS`
* `{% load i18n %}` and use `{% trans %}` or `{% blocktrans %}` in templates
* `from django.utils.translation import ugettext_lazy as _` and wrap strings in `_()` in `*.py` files


## Determining client language

`LocaleMiddleware` tries to resolve the user's locale by:

1. A language prefix (like `/en/`) in URL
1. Looks for `LANGUAGE_SESSION_KEY` in user session
1. Looks for `django_language` (or otherwise define by `LANGUAGE_COOKIE_NAME`) cookie
1. `Accept-Language` header


## Language URL prefix

Use `i18n_patterns` helper to wrap URL paths with a language prefix.


## `LocaleMiddleware`

It determines the proper translation object to install based on the request.
It sets `Content-Language` header in the response.
`LocaleMiddleware` must come before `CommonMiddleware` and after `SessionMiddleware` to properly know the current language.


## What should we translate?

* Static data (copy, menu text, etc.)
* Dynamic data?


## Generating translation objects

`$ python manage.py makemessages -l 'zh_CN'`

Generates an object file for the Chinese language, which contains messages that should be translated.
Note that the Django settings it uses the format e.g. `zh-cn` but the `makemessages` command uses e.g. `zh_CN`.

`$ python manage.py compilemessages`

Make sure you do not have your virtual environment directory in the root of your Django project directory!
Django will try to compile messages for all the packages in that directory.
Sometimes Django will mark strings as fuzzy, which has to be manually removed after you're sure a particular translation is correct.


## Dynamic string translations

You can use a thirdparty service or a package like `django-modeltranslation` to store translations with the model.


## Additional tips

* Use `translate_url` to translate URL patterns
* Use `get_available_languages` to get all languages available to translate to (useful for showing "Switch language" links)
