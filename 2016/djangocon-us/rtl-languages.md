# Beyond PO: How to make Django work for RTL languages
## Cho Garcia

### Ideas

### Planning

* How many languages?
* Linked translations?
* fallbacks?
* url or subdomain based?
* should we translate urls? (probably not)

### Dos and Don'ts

#### Do

* add translations without changing models and views
* store translations in same table
* handle more than just text fields

#### Don't

* Translate URLs
* Use obstructive third-party packages
* Rely on third-party APIs
* ORM query hacks

### Process

* `LocaleMiddleware`
* `LANGUAGES` setting
* `ugettext_lazy`
