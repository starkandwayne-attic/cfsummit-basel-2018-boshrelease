# BOSH release for cfsummit

This BOSH release and deployment manifest deploy a cluster of cfsummit.

## Usage

This repository includes base manifests and operator files. They can be used for initial deployments and subsequently used for updating your deployments:

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=cfsummit
git clone https://github.com/cloudfoundry-community/cfsummit-boshrelease.git
bosh deploy cfsummit-boshrelease/manifests/cfsummit.yml
```

If your BOSH does not have Credhub/Config Server, then remember `--vars-store` to allow generation of passwords and certificates.

### Update

When new versions of `cfsummit-boshrelease` are released the `manifests/cfsummit.yml` file will be updated. This means you can easily `git pull` and `bosh deploy` to upgrade.

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=cfsummit
cd cfsummit-boshrelease
git pull
cd -
bosh deploy cfsummit-boshrelease/manifests/cfsummit.yml
```
