# CakePHP Pluginception

A demo application to try out loading plugins as a whole in `Application.php` vs. creating a stand-alone plugin which contains all the dependencies in itself.

## Loading plugins

### To load EE plugins

- Require `pluginception/ee` vendor package/plugin:
    ```sh
    composer require pluginception/ee
    ```

    If you have `pluginception/ce` already required:
    ```sh
    composer remove pluginception/ce
    composer require pluginception/ee
    ```

- Uncomment `$this->addPlugin(\Pluginception\Ee\EePlugin::class);` (line no. 67) and comment out `$this->addPlugin(\Pluginception\Ce\CePlugin::class);` (line no. 66) in `src/Application.php` file.

The EE plugin will load all the CE, all the plugins of CE plugin(see `plugins/Ce/plugins`), EE plugin itself and all the plugins of EE plugin(see `plugins/Ee/plugins`).

<img src="https://raw.githubusercontent.com/ishanvyas22/cakephp-pluginception/298c26b5a3fcfe936f16deef0e8712c2fdc1b635/inception.gif" alt="gif" width="405" height="280">

### To load CE plugins

Do the inverse of what you did to load EE, Duh!

## References

- https://stackoverflow.com/a/70184257/3370200
- https://getcomposer.org/doc/05-repositories.md#path
- https://getcomposer.org/doc/articles/troubleshooting.md#i-have-a-dependency-which-contains-a-repositories-definition-in-its-composer-json-but-it-seems-to-be-ignored-
