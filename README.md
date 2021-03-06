# Magento 2 Useful Commands
Below is the list of most important CLI commands for Magento 2 that I have found useful. To use these commands you will need to have SSH access to your server or use the Command Line for local access.
#### Install Magento2 Using Command Line ([Reference](https://devdocs.magento.com/guides/v2.2/install-gde/install/cli/install-cli-install.html))
```sh
$ php bin/magento setup:install --backend-frontname="admin" --key="admin" --session-save="files" --db-host="localhost" --db-name="magento_2_db" --db-user="root" --db-password="root" --base-url="http://local.magento.com/" --base-url-secure="https://local.magento2.com/" --admin-user="admin" --admin-password="admin123" --admin-email="admin@example.com" --admin-firstname="Admin" --admin-lastname="Admin"
```
#### Setup Upgrade Using Command Line
```sh
$ php bin/magento setup:upgrade
# Shortcut Command:
$ php bin/magento s:up
```
If you don’t want to remove pub/static files while installing/updating database then use following command.
```sh
$ php bin/magento setup:upgrade --keep-generated
# Shortcut Command:
$ php bin/magento s:up --keep-generated
```
#### Cache Clean Using Command Line
```sh
$ php bin/magento cache:clean
# Shortcut Command:
$ php bin/magento c:c
```
#### Cache Flush Using Command Line
```sh
$ php bin/magento cache:flush
# Shortcut Command:
$ php bin/magento c:f
```
#### View cache status Using Command Line
```sh
$ php bin/magento cache:status
```
#### Enable Cache Using Command Line
```sh
$ php bin/magento cache:enable [cache_type]
# Shortcut Command:
$ php bin/magento c:e [cache_type]
```
#### Disable Cache Using Command Line
```sh
$ php bin/magento cache:disable [cache_type]
# Shortcut Command:
$ php bin/magento c:d [cache_type]
```
#### Static Content Deploy Using Command Line (Use -f for force deploy on 2.2.x or later)
```sh
$ php bin/magento setup:static-content:deploy
# Shortcut Command:
$ php bin/magento s:s:d
```
#### Static Content Deploy For Particular Language Using Command Line
```sh
$ php bin/magento setup:static-content:deploy en_US
# Shortcut Command:
$ php bin/magento s:s:d en_US
```
#### Static Content Deploy For Magento Backend Theme Using Command Line (Working on 2.1.1 or later)
```sh
$ php bin/magento setup:static-content:deploy --theme="Magento/backend"
# Shortcut Command:
$ php bin/magento s:s:d --theme="Magento/backend"
```
#### Static Content Deploy For Specific Themes Using Command Line (Working on 2.1.1 or later)
```sh
$ php bin/magento setup:static-content:deploy --theme Magento/luma --theme Magento/second_theme
# Shortcut Command:
$ php bin/magento s:s:d --theme Magento/luma --theme Magento/second_theme
```
#### Exclude Themes on Static Content Deploy and does not minify HTML files Using Command Line (Working on 2.1.1 or later)
```sh
$ php bin/magento setup:static-content:deploy en_US --exclude-theme Magento/luma --no-html-minify
# Shortcut Command:
$ php bin/magento s:s:d en_US --exclude-theme Magento/luma --no-html-minify
```
#### Reindexing Using Command Line
```sh
$ php bin/magento indexer:reindex
# Shortcut Command:
$ php bin/magento i:rei
```
#### View the list of indexers Using Command Line
```sh
$ php bin/magento indexer:info
# Shortcut Command:
$ php bin/magento i:i
```
#### View indexer status Using Command Line
```sh
$ php bin/magento indexer:status
# Shortcut Command:
$ php bin/magento i:st
```
#### Indexer reset Using Command Line
```sh
$ php bin/magento indexer:reset
# Shortcut Command:
$ php bin/magento i:res
```
#### Show the mode of all indexers Using Command Line
```sh
$ php bin/magento indexer:show-mode
# Shortcut Command:
$ php bin/magento i:sh
```
#### See all modules Status Using Command Line
```sh
$ php bin/magento module:status
# Shortcut Command:
$ php bin/magento mo:s
```
#### Enable module Using Command Line
```sh
$ php bin/magento module:enable Namespace_Module
# Shortcut Command:
$ php bin/magento mo:e Namespace_Module
```
#### Disable module Using Command Line
```sh
$ php bin/magento module:disable Namespace_Module
# Shortcut Command:
$ php bin/magento mo:d Namespace_Module
```
#### Uninstall Module Using Command Line
```sh
$ php bin/magento module:uninstall Namespace_Module
# Shortcut Command:
$ php bin/magento mo:u Namespace_Module
```
#### Check Current Mode Using Command Line
```sh
$ php bin/magento deploy:mode:show
# Shortcut Command:
$ php bin/magento d:m:sh
```
#### Change To Developer Mode Using Command Line
```sh
$ php bin/magento deploy:mode:set developer
# Shortcut Command:
$ php bin/magento d:m:se developer
```
#### Change To Production Mode Using Command Line
```sh
$ php bin/magento deploy:mode:set production
# Shortcut Command:
$ php bin/magento d:m:se production
```
#### Run the single-tenant Compiler Using Command Line
```sh
$ php bin/magento setup:di:compile
```
#### Unlock Admin User Using Command Line
```sh
$ php bin/magento admin:user:unlock adminusername
```
#### Enable Maintenance Mode Using Command Line
```sh
$ php bin/magento maintenance:enable
```
#### To enable maintenance mode for all clients except 192.0.0.1 and 192.0.0.2:
```sh
$ php bin/magento maintenance:enable --ip=192.0.0.1 --ip=192.0.0.2
```
#### To clear the list of IPs.
```sh
$ php bin/magento maintenance:enable --ip=none
```
#### Disable Maintenance Mode Using Command Line
```sh
$ php bin/magento maintenance:disable
```
#### Check Maintenance Mode Status Using Command Line
```sh
$ php bin/magento maintenance:status
```
#### Allow IP on Maintenance Mode Using Command Line
```sh
$ php bin/magento maintenance:allow-ips --ip=192.0.0.1 --ip=192.0.0.2
```
#### Set Magento crontab Using Command Line
```sh
$ php bin/magento cron:install --force
```
Use --force to rewrite an existing Magento crontab.
To view the crontab, enter the following command as the Magento file system owner.
```sh
$ crontab -l
```
#### Remove Magento crontab Using Command Line
```sh
$ php bin/magento cron:remove
```
I hope this Magento technical note helped you find what you were looking for. This is a comprehensive list of all useful Magento 2 commands; bookmark it for your future reference.