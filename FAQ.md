## FAQ from Workshop hosted on 07 MAY 2020 at GitHub Satellite

- Q: How safe it is to use 3rd party actions? any audit there? I am a bit afraid passing keys to some non-certified actions
  - A:
    - 3rd party actions should be treated like using any 3rd party library. i.e. if you use a npm module, a ruby gem, a nuget package, a docker container, etc. You would want to do your own validation of the security risk for that module. Actions are similar, in that these are driven by someone else so the code may change
    - That said, we recommend using something like:
      - `uses: actions/checkout@v2` which specifies a specific version. You can also specify a specific sha to ensure it even more: `uses:action/checkout@1cbfa...`
- Q: Are there any reqs for the action to appear on the market, for example security standards? Are network calls done from the actions monitored?
  - A: They must be open source repositories to be posted on the GitHub Marketplace, and as open-source may or may not have malicious code, it would be up to the user of that code to do security checks. We do some automated scanning of repositories for things that break out ToS, but I don't know the expansiveness of it in terms of specific malicious execution paths. We would recommend looking into dependency scanning and static code analysis tools that would meet your security standards instead, if this is a concern
- Q: Are the slides going to be available? What about the recording?
  - A: Slides are available [in the repo](https://github.com/githubsatelliteworkshops/cd-with-actions/blob/master/satellite-2020-continuous-delivery-with-actions.pdf). The recording will be emailed out sometime after the session
- Q: I am looking for deploying to Azure. Would this workshop cover that too?
  - A: This workshop leverages AWS, however the concepts can be applied to Azure at a high level. There are many [official Azure actions available here](https://github.com/Azure/actions#github-actions-for-azure)
- Q: Is there any tutorial on how to setup S3 and the relevant secret/access keys?
  - A: This would be directed to the [AWS docs here](https://aws.amazon.com/s3/getting-started/?nc=sn&loc=5) and [here](https://docs.aws.amazon.com/general/latest/gr/aws-sec-cred-types.html#access-keys-and-secret-access-keys)
- Q: What song is being played in the background music?
  - A: Lost by Danny Evo
- Q: What scopes do I need on my PAT
  - A: [‘read:packages’] and repo?
- Q: There is a `labeled` section on the workflow, does this mean that every PR needs a label attached? What happens if no labels were attached?
  - A: The types condition means it will only trigger off the `pull_request.labeled event`. Further reading on types can be [found here](https://help.github.com/en/actions/reference/workflow-syntax-for-github-actions#onevent_nametypes). More info on the `pull_request` event's types can be [found here](https://help.github.com/en/actions/reference/events-that-trigger-workflows#pull-request-event-pull_request)
- Q: What AWS resources do we need to remove in order to avoid billing after the workshop?
  - A: S3 bucket, and stop the Lambda function (AWS Services -> Lambda -> Functions). You can delete the stack in CloudFormation too
  
  ---
  
  ## Resource slide links
  
- [GitHub Actions - CI Learning Lab](https://lab.github.com/githubtraining/github-actions:-continuous-integration)
- [GitHub Actions - GitHub Package Registry (GPR) Learning Lab](https://lab.github.com/githubtraining/github-actions:-publish-to-github-packages)
- [GitHub Actions - CD with AWS Learning Lab](https://lab.github.com/githubtraining/github-actions:-continuous-delivery-with-aws)
- [GitHub Actions help documentation](https://help.github.com/en/actions)
- [GitHub Actions on the GitHub Marketplace](https://github.com/marketplace?type=actions)  
