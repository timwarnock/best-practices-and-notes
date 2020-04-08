## Jenkins Notes

Declarative and Scripted syntax,

https://jenkins.io/doc/book/pipeline/syntax/


### slack integration

Create `token` for [Jenkins slackSend()](https://my.slack.com/services/new/jenkins-ci).

You can customize the name and image, and create as many tokens as you want (for different builds or build statuses).


#### e.g.,
```
      slackSend(
        channel: '#example',
        teamDomain: 'sharedtech-capitalone',
        token: 'tokenfromabove',
        color: '#ff0000',
        message: "some message ${someVariable}"
      )
```

Alternatively, save the `token` in Jenkins Credentials using type `secret text`. You can name the token whatever you want, and then refer to it by name, e.g.,

```
      slackSend(
        channel: '#example',
        teamDomain: 'sharedtech-capitalone',
        tokenCredentialId: 'example-slack',
        color: '#ff0000',
        message: "some message ${someVariable}"
      )
```

See [slackSend docs](https://jenkins.io/doc/pipeline/steps/slack/) for more information.



### aws integration

https://github-pages.cloud.capitalone.com/emerging-products/blog/2018/02/22/jenkins2x-and-aws.html


### vault integration

https://github.cloud.capitalone.com/prometheus/perf-test/blob/ec40122edd2891a20f1ac94cb7117b7047ec926c/Jenkinsfile

https://github.cloud.capitalone.com/CloudX/phoenix-db/blob/c800dfa9b4d8b6bcf70d847af3bb2b4b6831713b/Jenkinsfile

