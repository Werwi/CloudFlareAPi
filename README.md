# CloudFlare API

Simple PHP api for CloudFlare

![beta](https://img.shields.io/badge/status-beta-yellow.svg?style=for-the-badge)
![web](https://img.shields.io/badge/web-werwi.eu-brightgreen.svg?style=for-the-badge) 
--- 
## Main init
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
```

## Register domain
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
$domain->name = ""; //Domain
$domain->zoneRegister();
```

## Information about domain
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
$domain->name = ""; //Domain
$domain->zoneInfo();
```

## Turn DEV Mode on domain
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
$domain->zoneid = ""; //Domain ID (Domain id is in zoneInfo());
$domain->zoneDevMode('on'); //Value: on or off 
```

## Information about DEV Mode on domain
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
$domain->zoneid = ""; //Domain ID (Domain id is in zoneInfo());
$domain->zoneDevModeInfo();
```

## Domain delete
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
$domain->zoneid = ""; //Domain ID (Domain id is in zoneInfo());
$domain->zoneRemove();
```

## DNS records list
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
$domain->zoneid = ""; //Domain ID (Domain id is in zoneInfo());
$domain->dnsList();
```

## Add DNS record
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
$domain->zoneid = ""; // Domain ID (Domain id is in zoneInfo());
$domain->dnsAdd('A', 'test.werwi.eu', '173.249.28.105', true); //Record type, domain, content, proxied on CloudFlare
```
SRV record:
```php
array(
	'type' => 'SRV',
	'data' => array(
		"name"=>"testsrv",
		"ttl"=>120,
		"service"=>"_ts3",
		"proto"=>"_udp",
		"weight"=>5,
		"port"=>11,
		"priority"=>0,
		"target"=>"testsrv.domain.com"
		)
)
```


## DNS record update
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
$domain->zoneid = ""; //Domain ID (Domain id is in zoneInfo());
$domain->dnsUpdate('cb231ddd3092f3ed8...', 'A', 'test.werwi.eu', '173.249.28.105', true); //Record ID (in DNS record list), record type, content, proxied on CloudFlare
```

## Remove DNS record
```php
$domain = new CloudFlare();
$domain->apikey = ""; //Cloudflare API key
$domain->email = ""; //Cloudflare Email
$domain->zoneid = ""; // Domain ID (Domain id is in zoneInfo());
$domain->dnsRemove('cb231ddd3092f3ed8...'); //Record ID (in DNS record list)
```