jQueryBundle
===============
This bundle provides several jQuery libaries, such as jQuery itself, jQuery UI, and jQuery mobile.

##Install
Add the bundle to your AppKernel::registerBundles() method.
```php
        class AppKernel extends Kernel
        {
            public function registerBundles()
            {   
                $bundles = array(
                    
                    new lx\jQueryBundle\lxjQueryBundle,
                    
                );
            }
        }
```
##Use
To use the components you have to include it with assetic in twig.
```twig
        {% javascripts filter='?yui_js' output='js/application.js'
            '@lxjQueryBundle/jQuery-latest.js'
            '@lxjQueryBundle/jQueryUI/ui/jquery.ui.core.js'
            '@lxjQueryBundle/jQueryUI/ui/jquery.ui.widget.js'
            '@lxjQueryBundle/jQueryUI/ui/jquery.ui.mouse.js'
            '@lxjQueryBundle/jQueryUI/ui/jquery.ui.position.js'%}
            <script type="text/javascript" src="{{ asset_url }}"></script>
        {% endjavascripts %}
```
Just pick out the files you need for your project, include them and GO!

        Note: Watch out for the dependencies of thecomponents. For example, widget and mouse need the core component.

The filter attribute is optional, but we highly recommend using it because of none of the javascript and css files are minified for development reasons.
We further recommend reading the article about assetic in the Symfony2 documentation. -> http://symfony.com/doc/2.0/cookbook/assetic/asset_management.html
