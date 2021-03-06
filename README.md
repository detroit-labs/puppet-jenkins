# Jenkins Puppet Module for Boxen

This installs the [Jenkins CI-server](http://jenkins-ci.org) on your machine.

## Usage

```puppet
include jenkins
```

Browse to [http://jenkins.dev](http://jenkins.dev).

### Options

You can set optional `$jenkins_max_heap_size` and `$jenkins_max_perm_size` vars in `site.pp` to control heap and permgen sizes
in Jenkins Java VM via [java command line arguments](https://wiki.jenkins-ci.org/display/JENKINS/Starting+and+Accessing+Jenkins):

```puppet
node 'myhostname.local' {
  # core modules, needed for most things
  include dnsmasq
  …

  # jenkins
  $jenkins_max_heap_size = "6G"
  $jenkins_max_perm_size = "512M"
  include jenkins

  …
}
```

## Required Puppet Modules

* `boxen`
* `homebrew`
* `nginx`

## Environment

Once installed, you can access the following variables in your environment, projects, etc:

* BOXEN_JENKINS_PORT: The port on which Jenkins listens
* BOXEN_JENKINS_HOME: The Jenkins home-directory
