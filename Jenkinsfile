pipeline {
  agent any
  stages {
    stage('Test Ovirt Node Status') {
      steps {
        sh '''#! /bin/bash

# test network status - make sure we're inside the network
# test nas status - ensure that files are available
# test ilo status - ensure that ilo is up and running
# if ilo status fails, build fails.
# test ovirt-node status - ensure that ovirt-node dns status responds
# if ovirt-node status fails, build fails.
# test nodectl status - ensure node health is 100%
# if nodecctl fails, run install.'''
      }
    }
    stage('Build Ovirt Node Server') {
      steps {
        sh '''#! /usr/bin/python

# download git repo
# download dependencies -- ilo python library
# access ilo endpoint
# mount virtual disk
# set single time boot to disk
# timer should run out and start autoinstall
# install should finish
# test nodectl check to ensure that the server is healthy
# test hosted engine status - if fails, being hosted engine build.
'''
      }
    }
    stage('Build Ovirt-Engine Self hosted Engine') {
      steps {
        sh '''#! /bin/bash

# run self hosted install
# set a timer to wait for hosted engine to deploy completely
# test that data domain is working
# test datacenter status - if datacenter fails, create datacenter.'''
      }
    }
    stage('Build MCIT Datacenter') {
      steps {
        sh '''#! /usr/bin/python

# download dependencies - ovirtsdk4
# ensure storage domains are setup
# set maintenance on host
# create datacenter
# create cluster
# add host to cluster -- this could be solved during the previous build
# reboot the host to test that the datacenter recovers successfully.'''
      }
    }
  }
}