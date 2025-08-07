# CSS/ Asset pipeline iekš Rails:

## Asset pipeline:

https://medium.com/@adamzerner/rails-asset-pipeline-982f3ea75596 (labāks guide, vienkāršāk)

https://guides.rubyonrails.org/asset_pipeline.html#evolution-of-asset-management-techniques

## How SASS works:

https://www.codecademy.com/resources/blog/what-is-sass

## Tailwind benefits:

https://www.swyx.io/why-tailwind?ck_subscriber_id=1095223109

## Tailwind vs SASS:

https://dev.to/this-is-learning/tailwind-vs-sassscss-structure-and-consistency-over-style-and-comfort-44cd

## Tailwind vs Bootstrap:

https://bootrails.com/blog/tailwind-vs-bootstrap/

# Bootstrap un Tailwind install:

## Pirms veic gem install:

- Vajag gems ielikt lokāli projektā, izpildot terminālī

  ```
  bundle config set --local path 'vendor/bundle'
  ```

- Iekš `.gitignore` faila ielikt `vendor`
- Terminālī palaist
  ```
  bundle install
  ```

## Install Bootstrap gem:

- Ieliec gem: https://github.com/twbs/bootstrap-rubygem
- Izvēlēties atbilstošo sass engine (dartsass-rails: https://github.com/rails/dartsass-rails )
- Terminālī palaist
  ```
  bundle install
  ```
- Nomaini `app/assets/stylesheets/application.css` uz `app/assets/stylesheets/application.scss`
- Ieliec tajā failā `@import "bootstrap";`
- Terminālī palaist

  ```
  bin/rails dartsass:install
  ```

- Trumpāk jāizmanto būs `bin/dev` nevis `rails s`, lai palaistu app

## Uninstall bootstrap gem:

- Izņem gem no Gemfile

- Terminālī palaist
  ```
  bundle clean
  ```
- Atgriež atpakaļ `app/assets/stylesheets/application.scss` uz `app/assets/stylesheets/application.css`
- Noņem `@import "bootstrap";` importu
- Izdzēst `builds` folder, ja citi gems nelieto (pasearchot par to var internetā, kpc vajag)
- Noņem `.gitignore` `builds` folder ignore

## Install Tailwind gem:

- Ieliec gem: https://github.com/rails/tailwindcss-rails
- Izvēlies labāk gem "tailwindcss-rails", "~> 3.3.1" (lai mazāks čakars)
- Terminālī palaist
  ```
  bundle install
  ```
- Pēc install terminālī palaist
  ```
  bin/rails tailwindcss:install
  ```
  Izveidojas šādi faili:
  - `config/tailwind.config.js`
  - `app/assets/stylesheets/application.tailwind.css`
  - `Procfile.dev`
  - Updates `.gitignore`
- Trumpāk jāizmanto būs `bin/dev` nevis `rails s`, lai palaistu app

## Uninstall Tailwind gem:

- Izdzēst
  - `tailwind.config.js`
  - `app/assets/stylesheets/application.tailwind.css`
  - `builds` folder, ja citi gems nelieto (pasearchot par to var internetā, kpc vajag)
- Noņem `.gitignore` `builds` folder ignore
- Izņem gem no Gemfile
- Terminālī palaist
  ```
  bundle clean
  ```
- Iekš `app/views/layouts/application.html.erb` noņem `<%= stylesheet_link_tag "tailwind", "inter-font", "data-turbo-track": "reload" %>`

# Dokumentācijas stilizēšanai:

- Bootstrap: https://getbootstrap.com/docs/5.3/getting-started/introduction/
- Tailwind: https://v3.tailwindcss.com/docs/text-color#setting-the-text-color
- Atceries skatīties pareizo versiju dokumentācijai (kas atbilst vai ir zemāka par ielādēto gem versiju).
- Lai redzētu gem versiju, terminālī palaid
  ```
  bundle list
  ```
