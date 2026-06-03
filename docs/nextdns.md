# NextDNS

## Configuration

### Example

```json
{
  "settings": [
    {
      "provider": "nextdns",
      "endpoint": "abcdef/0123456789abcdef",
      "ip_version": "ipv4",
      "ipv6_suffix": ""
    }
  ]
}
```

### Compulsory parameters

- `"endpoint"` is the Linked IP endpoint from your NextDNS account. It has the format `<Endpoint ID>/<API GUID>`, where the Endpoint ID is 6 hexadecimal characters and the API GUID is 16 hexadecimal characters (e.g. `abcdef/0123456789abcdef`).

### Optional parameters

- `"ip_version"` can be `ipv4` (A records), or `ipv6` (AAAA records) or `ipv4 or ipv6` (update one of the two, depending on the public ip found). It defaults to `ipv4 or ipv6`.
- `"ipv6_suffix"` is the IPv6 interface identifier suffix to use. It can be for example `0:0:0:0:72ad:8fbb:a54e:bedd/64`. If left empty, it defaults to no suffix and the raw temporary IPv6 address of the machine is used in the record updating. You might want to set this to use your permanent IPv6 address instead of your temporary IPv6 address.

> **Note:** The domain is always fixed to `link-ip.nextdns.io` and does not need to be specified.

## Domain setup

NextDNS supports updating Linked IP via a DDNS hostname. If you're already using a DDNS service, configure your DDNS domain in the Linked IP card instead.

1. Create an account on the [nextdns website](https://nextdns.io/)
1. Go to your [account page](https://my.nextdns.io/), login and setup Linked IP
1. Click `Show advanced options` in the Linked IP card
1. Copy the endpoint string — it looks like `abcdef/0123456789abcdef` (`<Endpoint ID>/<API GUID>`)
1. Set `"endpoint"` in your configuration file to that value

See the [nextdns website](https://nextdns.io/)
