# Test OAuth2 sunucusu

Test sunucusunu böyle başlatıyoruz:
``` shell
wrangler dev
```

Auth code'u şu şekilde alabiliriz:
```shell
curl 'localhost:8787/auth?response_type=code&client_id=F5CAA82F-E2CF-4F21-A745-471ABE3CE7F8&
redirect_uri=https://kimlikdao.org&scope=Temel-Bilgileri' 
```

Bir sonraki adım auth code ile `access_token` almak:
```shell
curl localhost:8787/token -d "grant_type=authorization_code&code=AC22345678902&client_id=F5CAA82F-E2CF-4F21-A745-471ABE3CE7F8&client_secret=B97B789F-9D0F-48AF-AD09-0721979D0E9F"
```

Aldığımiz `access_token` ile kullanıcı `Temel-Bilgileri`'ne ulaşabiliriz:
```shell
curl localhost:8787/temel-bilgileri -H "Authorization: Bearer AT2345678902"
```
