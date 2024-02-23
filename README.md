## Drupal Development Helper Recipe

This recipes' intention is to showcase the features and power of recipes. It installs various useful contrib modules and creates an 'Editor' user role with permissions to edit/delete and Article content.

### Prerequisites:
1. Add the following snippet in your `composer.json` on the Drupal 9.4+ site you'll want to use it:

   ```shell
   "balintpekker/drupal_base_recipe": {
       "type": "git",
       "url": "https://github.com/balintpekker/drupal_base_recipe"
   }
   ```
2. Add the following patch to the same `composer.json` file to enable the recipe features:
   ```shell
   "patches": {
       "drupal/core": {
           "Distribution and Recipes Initiative (https://www.drupal.org/project/distributions_recipes)": "https://git.drupalcode.org/project/distributions_recipes/-/raw/patch/recipe-10.2.x.patch"
       }
   }
   ```


### Installation:

Once you've met the requirements above, run the following commands:

```shell
$ composer require balintpekker/drupal_base_recipe
$ composer install
```

If the composer install ran successfully, you can enable the recipe with the following commands:

```shell
$ cd ./web; php ./core/scripts/drupal recipe ../vendor/balintpekker/drupal_base_recipe; cd -
```

*Note: We assume the Drupal core is in `web`. If the Drupal core is placed somewhere else, you'll need to adjust the script above. It's important to run the php script from DRUPAL_ROOT.*

*Note: If you are using [Composer Installers Extender](https://github.com/oomphinc/composer-installers-extender), and configured `drupal-recipe` type packages to be placed in `web/recipes/contrib/{$name}`, you also need to adjust the php command above.*
