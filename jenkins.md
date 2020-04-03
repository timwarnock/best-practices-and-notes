## Jenkins Notes

### slack integration

Create `token` for Jenkins slackSend()

https://my.slack.com/services/new/jenkins-ci

https://jenkins.io/doc/pipeline/steps/slack/


#### e.g.,
```
      slackSend(
        channel: '@timothy.warnock',
        teamDomain: 'sharedtech-capitalone',
        token: 'C2UdP3ziEwupFr3JLV3TDsKF',
        color: '#ff0000',
        message: "some message ${someVariable}"
      )

```


### aws integration

https://github-pages.cloud.capitalone.com/emerging-products/blog/2018/02/22/jenkins2x-and-aws.html


### vault integration

https://github.cloud.capitalone.com/prometheus/perf-test/blob/ec40122edd2891a20f1ac94cb7117b7047ec926c/Jenkinsfile

https://github.cloud.capitalone.com/CloudX/phoenix-db/blob/c800dfa9b4d8b6bcf70d847af3bb2b4b6831713b/Jenkinsfile

