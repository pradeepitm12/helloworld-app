@Library('github.com/fabric8io/osio-pipeline@master') _

osio {
  config runtime: 'java', version: '1.8.1'

  ci {
    def resources = processTemplate(params: [])
    build resources: resources
  }

  cd {
    echo "Running CD build.........."
    def resources = processTemplate(params: [])

    build resources: resources
    deploy resources: resources, env: 'stage'
    deploy resources: resources, env: 'run', approval: 'manual'

  }
}
