Войдите в облако, перейдите в каталог defaut.
Создайте федерацию с параметрами

Issuer:       http://ad.yc-iam.local/adfs/services/trust
SSO method:   POST
SSO URL:      https://ad.yc-iam.local/adfs/ls
              [X] Автоматически создавать пользоватлей

Нажмите на созданную федерацию и добавьте сертификат

-----BEGIN CERTIFICATE-----
MIIC2jCCAcKgAwIBAgIQcPjJRpm3GZ1GX7ZHo5IuxzANBgkqhkiG9w0BAQsFADAp
MScwJQYDVQQDEx5BREZTIFNpZ25pbmcgLSBhZC55Yy1pYW0ubG9jYWwwHhcNMTkw
OTMwMTA1MzQyWhcNMjAwOTI5MTA1MzQyWjApMScwJQYDVQQDEx5BREZTIFNpZ25p
bmcgLSBhZC55Yy1pYW0ubG9jYWwwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEK
AoIBAQCqNuA+sg27vlGr9RpxqjFMM6nf1zdLpoynq6yK4t8NuVDkP4R2L15RQF5q
6J+js14PUKK614fQhBjiX7h0wJA778bMT5upxEtuwSEpgLSiVhy6qQLXDu3VPcx8
Q73aS2TEWFwdJjvoo2fBkSdneWUod27HsxhrHgwwsB8R68GGvpXF+iUtf27f7sfY
tDVNTjMMd1dNB6Ax+jtEbzNKyjSe/pimRL9pO94Mh9h0gIEDkuNfv7OZ57SHiTlR
RQFgaoGLx+44appo0B/RFr4Sau8IPNBbS7NV3QfJtQGDMavU9Vd52AuFWuKY2DRj
U7kLUd8WOZe4XgzhFd8bOvM+GCQHAgMBAAEwDQYJKoZIhvcNAQELBQADggEBADXL
nk/qgsfJhlHAzMA94Oj50rK7cu25Puy8NBU9QafMJ6779OflPBL+0s/bTCxK1frA
UozLI1nWP6Rh7yTsOThJtMD2iOVKAZq19zwkITBrj1SbIJFvXyD5Xp/zVCj330Be
IxsK9ahh1ZV8LXwZA1aiDgob9e0zaU/kI8qCh+WSDNViLCQkaDkujT1VZHfZ1rDt
vUGTKR1c0971hogG/3e02CE4vi0fMQG2UydBJTu/3qBtwzYLNyC3wT+I2WSZyrws
pyGbIIgQUH9aYOlz/H6li98vQEJd5xM/l+FGdXXo0HiQ5CEtBh9C7uQon3QyL5mM
04VLkWHJhg6thi0AVqI=
-----END CERTIFICATE-----


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
LDAP Attribute:  User-Principal-Name
Claim Type:      Name ID


Перейдите в браузере по ссылке
https://console.cloud.yandex.ru/federations/<идентификатор федерации>

