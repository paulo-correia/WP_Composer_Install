Pré Requisitos:

PHP
Composer https://getcomposer.org/
Editor de Texto de sua preferência

Está é a instalação **sempre** da última versão do WordPress no diretório onde estiver este config.json:

```
{
    "name": "paulo-correia/wp_composer_install",
    "description": "Instalação do WordPress com o Composer",
    "minimum-stability": "stable",
    "license": "MIT",
    "authors": [
           {
            "name": "Paulo Correia",
            "role": "Developer",
            "homepage": "https://github.com/paulo-correia"
        }
    ],
    "config": {
        "vendor-dir": "vendor"
    },
    "repositories": [
        {
            "type": "package",
                "package": {
                    "name": "paulo-correia/wordpress-pt_br",
                    "version": "master",
	                "dist": {
                       "type": "zip",
                        "url": "https://br.wordpress.org/latest-pt_BR.zip",
                        "reference": "master"
                    }
               }         
        },
        {
            "type":"composer",
            "url":"https://wpackagist.org"         
        }        
    ],
    "require": {
        "koodimonni/composer-dropin-installer": "dev-master",
        "paulo-correia/wordpress-pt_br": "dev-master"
    },
    "extra": {
        "dropin-paths": {
		    "/": ["vendor:paulo-correia"]
	    }
    }
}

```
Caso queira pode inserir um plugin ou um tema, bastando alterar o config.json adicionando uma virgula após o ```"paulo-correia/wordpress-pt_br": "dev-master"```, inserindo uma nova linha e nesta colocar o tema ou plugin que quer instalar junto, exemplo:
```
      "paulo-correia/wordpress-pt_br": "dev-master",
	    "wpackagist-theme/hueman":"*"
```
Neste exemplo vai istalar o tema hueman.

Mais temas e plugins em [WordPress Packagist](https://wpackagist.org/)

Este json, foi baseado na idéia do [rudwolf](https://github.com/rudwolf) repositório: [base-wp-repo](https://github.com/rudwolf/base-wp-repo/tree/language_version/pt_BR)



