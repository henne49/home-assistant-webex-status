# home-assistant-webex-status
How to retrieve webex status into home-assistant.io

you have to fill in the snippet below
```
<<personid>>
<<token>>
```  
  
## How to retrieve Token and PersonID
  
## configuration in configuration.yaml  
```
sensor:  
  - platform: command_line
    name: Webex Teams Status using Rest
    command: "curl -H 'Authorization:Bearer <<token>> ' https://webexapis.com/v1/people/<<personid>>"
    # Since the response is JSON, we can parse out just the Status key
    value_template: "{{ value_json.status }}"
    scan_interval: 10
```
