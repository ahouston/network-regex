# network-regex
Curated List of Network Syslog Regular Expressions

## Overview
This project aims to provide a curated structure of regular expressions relating to network devices such as switches, routers or firewalls.

**Example:**
```
{
   "vendors": ["cisco","juniper"],
   "software": ["ios","ios-xe","ios-xr","junos"],
   "filters": ["LINK-3-UPDOWN","LINEPROTO-5-UPDOWN"],
   "regex": [
        {
            "description": "Interface down",
            "vendor": "cisco",
            "software": ["ios","ios-xe"],
            "regex": "%LINEPROTO-5-UPDOWN: Line protocol on Interface (?<interface_name>.+), changed state to down",
            "keys": ["interface_name"],
            "test_string": "001672: Apr 11 14:16:42.735 AFRICA: %LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to down",
            "filter": "LINEPROTO-5-UPDOWN"
        },
        {
            "description": "Interface up",
            "vendor": "cisco",
            "software": ["ios","ios-xe"],
            "regex": "%LINEPROTO-5-UPDOWN: Line protocol on Interface (?<interface_name>.+), changed state to up",
            "keys": ["interface_name"],
            "test_string": "001672: Apr 11 14:16:42.735 AFRICA: %LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to up",
            "filter": "LINEPROTO-5-UPDOWN"
        }

    ]
}
```

## Usage

The files are provided in JSON and YAML format, The monolithic files such as network-regex.json and network-regex.yaml are built from the individual JSON files used to store each regular expression object.

The aim is for these regular expressions to be ingested by a third party application for the purposes of matching and parsing syslog messages.
