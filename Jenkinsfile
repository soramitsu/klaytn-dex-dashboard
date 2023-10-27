@Library('jenkins-library' ) _

def pipeline = new org.js.AppPipeline(
    steps: this,
    test: false,
    buildDockerImage: 'build-tools/node:14-alpine',
    dockerImageName: 'klaytn/klaytn-dashboard',
    dockerRegistryCred: 'bot-klaytn-rw',
    packageManager: 'yarn',
    buildCmds: ['yarn build'],
    dockerImageTags: ['featureworkshop': 'local'],
    gitUpdateSubmodule: true)
pipeline.runPipeline()