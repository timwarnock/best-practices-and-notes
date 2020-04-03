## Jenkins Notes

### slack integration

Create `token` for Jenkins slackSend()
https://my.slack.com/services/new/jenkins-ci

#### e.g.,
```
      slackSend(
        channel: 'timothy.warnock',
        teamDomain: 'sharedtech-capitalone',
        token: 'C2UdP3ziEwupFr3JLV3TDsKF',
        color: '#ff0000',
        message: "some message ${someVariable}"
      )

```


### aws integration

https://github-pages.cloud.capitalone.com/emerging-products/blog/2018/02/22/jenkins2x-and-aws.html
