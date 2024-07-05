# Quickstart

## Dependencies

This module requires API key to function. You may sign up for a free API key at <https://www.ip2location.io/pricing>.

## Installation

To install this library using luarocks:

```bash

luarocks install ip2whois

```

## Sample Codes
### Lookup Domain Information

You can lookup domain information as below:

```lua
local ip2whois = require("ip2whois")

local apikey = "YOUR_API_KEY"

local domain = "locaproxy.com"
local whois = ip2whois:open(apikey)

local result = whois:lookup(domain)

print("version: " .. ip2whois.version)
print("domain: " .. result.domain)
print("domain_id: " .. result.domain_id)
print("status: " .. result.status)
print("create_date: " .. result.create_date)
print("update_date: " .. result.update_date)
print("expire_date: " .. result.expire_date)
print("domain_age: " .. result.domain_age)
print("whois_server: " .. result.whois_server)

print("registrar => iana_id: " .. result.registrar.iana_id)
print("registrar => name: " .. result.registrar.name)
print("registrar => url: " .. result.registrar.url)

print("registrant => name: " .. result.registrant.name)
print("registrant => organization: " .. result.registrant.organization)
print("registrant => street_address: " .. result.registrant.street_address)
print("registrant => city: " .. result.registrant.city)
print("registrant => region: " .. result.registrant.region)
print("registrant => zip_code: " .. result.registrant.zip_code)
print("registrant => country: " .. result.registrant.country)
print("registrant => phone: " .. result.registrant.phone)
print("registrant => fax: " .. result.registrant.fax)
print("registrant => email: " .. result.registrant.email)

print("admin => name: " .. result.admin.name)
print("admin => organization: " .. result.admin.organization)
print("admin => street_address: " .. result.admin.street_address)
print("admin => city: " .. result.admin.city)
print("admin => region: " .. result.admin.region)
print("admin => zip_code: " .. result.admin.zip_code)
print("admin => country: " .. result.admin.country)
print("admin => phone: " .. result.admin.phone)
print("admin => fax: " .. result.admin.fax)
print("admin => email: " .. result.admin.email)

print("tech => name: " .. result.tech.name)
print("tech => organization: " .. result.tech.organization)
print("tech => street_address: " .. result.tech.street_address)
print("tech => city: " .. result.tech.city)
print("tech => region: " .. result.tech.region)
print("tech => zip_code: " .. result.tech.zip_code)
print("tech => country: " .. result.tech.country)
print("tech => phone: " .. result.tech.phone)
print("tech => fax: " .. result.tech.fax)
print("tech => email: " .. result.tech.email)

print("billing => name: " .. result.billing.name)
print("billing => organization: " .. result.billing.organization)
print("billing => street_address: " .. result.billing.street_address)
print("billing => city: " .. result.billing.city)
print("billing => region: " .. result.billing.region)
print("billing => zip_code: " .. result.billing.zip_code)
print("billing => country: " .. result.billing.country)
print("billing => phone: " .. result.billing.phone)
print("billing => fax: " .. result.billing.fax)
print("billing => email: " .. result.billing.email)

print("nameservers: " .. table.concat(result.nameservers, ","))
```

### Convert Normal Text to Punycode

You can convert an international domain name to Punycode as below:

```lua
local ip2whois = require("ip2whois")
local whois = ip2whois:open("")

print(whois:getpunycode("täst.de"))
```

### Convert Punycode to Normal Text

You can convert a Punycode to international domain name as below:

```lua
local ip2whois = require("ip2whois")
local whois = ip2whois:open("")

print(whois:getnormaltext("xn--tst-qla.de"))
```

### Get Domain Name

You can extract the domain name from an url as below:

```lua
local ip2whois = require("ip2whois")
local whois = ip2whois:open("")

print(whois:getdomainname("https://www.example.com/exe"))
```

### Get Domain Extension

You can extract the domain extension from a domain name or url as below:

```lua
local ip2whois = require("ip2whois")
local whois = ip2whois:open("")

print(whois:getdomainextension("example.com"))
```