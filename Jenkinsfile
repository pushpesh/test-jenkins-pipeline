pipeline {
  agent any
  stages {
    stage('Init') {
      agent {
        node {
          label 'worker'
        }
        
      }
      steps {
        node(label: 'worker') {
          sh '/mts/git/bin/nimbus-test-launcher --plugin test-vpx --build vcenter:beta:ob-latest:layer1 --build server:beta:ob-latest:layer1 --test test-vpx-generic-4esx-fullInstall-vcva-12gbmem-allFlash --runName extendedConfig-$RANDOM --testvpxParams \'-i vsan.fvt.test.extendedClusterConfig.createVsanClusterWithExtendedConfigTests.py,vsan.fvt.test.extendedClusterConfig.largeClusterSupportTests.py --skip-cleanup --serial-only --extra-test-arguments observerNotRequired=1 -x clomdmemleakcheck=False -x observer=False --include-vsan-pyvmomi-async --vsan-fvt -x priority=P0\' --keepVMsOnFailure --waitForCompletion true'
        }
        
      }
    }
  }
}