Войдите в облако, перейдите в каталог defaut.
Создайте федерацию с параметрами

Issuer:       http://ad.yc-iam.local/adfs/services/trust
SSO method:   POST
SSO URL:      https://ad.yc-iam.local/adfs/ls
              [X] Автоматически создавать пользоватлей

Нажмите на созданную федерацию и добавьте сертификат
Сертификат находится в папке Рабочий Стол, Документы


Скопируйте идентификатор федерации. Откройте Remote Desktop к 
серверу ADFS. В панели управления ADFS выберите "Relaying Party Trusts"
и нажмите "Add Relaying Party Trust". Укажите "test" в качестве
"Display name", включите поддержку SAML 2.0 SSO, укажите в качестве URL

https://console.cloud.yandex.ru/federations/<идентификатор федерации>
например
https://console.cloud.yandex.ru/federations/ajepuddqdj1o5f3gvp4q
в качестве "Relaying party trust identifier" укажите тот же url.

Добавьте Claim "nameId" с параметрами:
name:            nameId

| LDAP Attribute: | Claim Type: |
|-----------------|-------------|
| User-Principal-Name | Name ID |
| EmailAddress | EmailAddres |
| Display Name | Name |

Перейдите в браузере по ссылке
https://console.cloud.yandex.ru/federations/<идентификатор федерации>

Войдите под учётной записью YC-IAM\User1 с паролем Tralala42
