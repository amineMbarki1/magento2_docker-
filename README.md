# magento2 docker compose configuration for local development

### 1- Include access keys in auth.json

### 2- Run "docker composer up"

### 3- Download magento 2.4.7

From the php-fpm container run

`composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition=2.4.7 /var/www/magento2`

### 4- Install Magento

From the php-fpm container run the installation command (Replace with configured values and host names with their corresponding docker containers)

```bash
bin/magento setup:install \
--base-url=http://your-domain.com \
--db-host=localhost \
--db-name=magentodb \
--db-user=magentouser \
--db-password='Str0ngPa$$w0rd' \
--admin-firstname=Admin \
--admin-lastname=User \
--admin-email=admin@your-domain.com \
--admin-user=admin \
--admin-password=admin123 \
--language=en_US \
--currency=USD \
--timezone=America/Chicago \
--use-rewrites=1
--elasticsearch-host=localhost
```
