[![Latest Stable Version](https://poser.pugx.org/cvette/google-tag-manager/v/stable)](https://packagist.org/packages/cvette/google-tag-manager) [![Total Downloads](https://poser.pugx.org/cvette/google-tag-manager/downloads)](https://packagist.org/packages/cvette/google-tag-manager) [![License](https://poser.pugx.org/cvette/google-tag-manager/license)](https://packagist.org/packages/cvette/google-tag-manager)

# Google Tag Manager Neos Plugin

This package includes Fusion prototypes, as well as a node type mixin for simple integration of the Google Tag Manager container code into your Neos CMS project.

## Usage

The following Fusion snippet adds the container script directly after the opening head tag and the fallback code directly after the body tag of your pages. By default the container is only included in Production context and the frontend.

    tagManagerScript = Vette.GoogleTagManager:ContainerScript {
		@position = 'before head'
	}

	tagManagerNoScript = Vette.GoogleTagManager:ContainerNoScript {
		@position = 'before body'
	}
   
The default Fusion code gets the container ID from a property 'containerId' of the site node. You can use the ContainerMixin to add the property to your site node.

    Your.Package:Site:
        superTypes:
            Vette.GoogleTagManager:ContainerMixin: TRUE
   
### Getting the container ID from settings
By overwriting the ContainerBase prototype you can get the container ID from settings or any other EEL expression.
    
    prototype(Vette.GoogleTagManager:ContainerBase) {
        containerId = ${Configuration.setting('Your.Package.containerId')}
    }      ...

## License

The GNU General Public License Version 3 (GPLv3). Please see [LICENSE](LICENSE) for more information.
