# Ux Modal Bundle with Twig, Alpine JS and Tailwind

![GitHub release (with filter)](https://img.shields.io/github/v/release/Pixel-Developpement/uxmodal-bundle?style=for-the-badge)
[![Dependency](https://img.shields.io/badge/twig-2/3-cca000.svg?style=for-the-badge)](https://twig.symfony.com/)

## Presentation

![](src/Resources/docs/img/screenshot.png)

A modal component with Tailwind and Alpine JS for Twig from the Penguin UI site : https://www.penguinui.com/components/modal

## Requirements

* PHP >= 8.0
* Twig >= 2.7
* Tailwind CSS >= 3.4
* Alpine JS >= 3
* Composer

## Installation

### Install the bundle

Execute the following [composer](https://getcomposer.org/) command to add the bundle to the dependencies of your
project:

```bash
composer require pixeldev/uxmodal-bundle
```

### Enable the bundle

Enable the bundle by adding it to the list of registered bundles in the `config/bundles.php` file of your project:

 ```php
 return [
     /* ... */
     Pixel\UxModalBundle\UxModalBundle::class => ['all' => true],
 ];
 ```

### Install Tailwind CSS and Alpine JS

See this documentation : https://www.penguinui.com/docs/getting-started

### Add bundle directory for Tailwind compilation 

Open tailwind.config.js and add the following line to the content table

```javascript
'./vendor/pixeldev/uxmodal-bundle/src/Resources/views/**/*.html.twig'
```

## Use
## General use

Here's an example of how to add a modal to your site:

```twig
{% embed '@UxModal/modal.html.twig' with {isFooterModal: true} %}
    {# Label for this button #}
    {% block buttonLabel %}Open Modal{% endblock %}
    {# Title for Modal #}
    {% block titleModal %}Title Modal{% endblock %}
    {# Body text for Modal #}
    {% block bodyModal %}
        Body text description
    {% endblock %}
    {# Add a button on a footer Modal #}
    {% block footerModal %}
        <button @click="modalIsOpen = false" type="button"
                class="{{ primaryButtonClass }} bg-black text-white hover:bg-primary-dark">
           Purchase
        </button>
    {% endblock %}
{% endembed %}
```

## Configurations

Todo