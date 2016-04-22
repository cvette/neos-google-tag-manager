[![Latest Stable Version](https://poser.pugx.org/cvette/lipsum/v/stable)](https://packagist.org/packages/cvette/google-tag-manager) [![Total Downloads](https://poser.pugx.org/cvette/lipsum/downloads)](https://packagist.org/packages/cvette/google-tag-manager) [![License](https://poser.pugx.org/cvette/lipsum/license)](https://packagist.org/packages/cvette/google-tag-manager)

# Google Tag Manager Neos Plugin

This package includes a TypoScript prototype, as well as a node type mixin for simple integration of the Google Tag Manager container code into your Neos CMS project.

## Usage

The following TypoScript adds the container directly after the opening body tag of your pages. By default the container is only included in Production context.

    prototype(TYPO3.Neos:Page)
        googleTagManager = Vette.GoogleTagManager:Container {
            containerId = 'GTM-...'
            @position = 'before body'
        }
    }
    
Getting the container id from settings is possible with this EEL expression: ```${Configuration.setting('Your.Package.containerId')}```

The container mixin can be used to add a containerId property to your site node type.

    Your.Package:Site:
        superTypes:
            Vette.GoogleTagManager:ContainerMixin: TRUE
            ...

You can then get the container id with this EEL expression: ```${q(site).properties.containerId}```

## License

The GNU General Public License Version 3 (GPLv3). Please see [LICENSE](LICENSE) for more information.
