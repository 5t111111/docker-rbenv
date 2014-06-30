# Dorker rbenv

Prepare image which is installed muliple versions of ruby and bundler for each versions. 

## Usage

You can use this image for your project soon. It's uploaded docker.io, [tcnksm/rbenv](https://index.docker.io/u/tcnksm/rbenv/).

```
docker pull tcnksm/rbenv
```

or in Dockerfile

```
FROM tcnksm/rbenv
```

Run it !

```
docker run -i -t tcnksm/rbenv bash -l -c 'rbenv global 2.0.0-p353; bundle ...'
```


## Build rbenv image

Install multiple versions of ruby by [rbenv](https://github.com/sstephenson/rbenv). you can define ruby verion which you want to use in `versions.txt`.


### Build image

```
docker build -t TAG .
```

Dockerfile execute belows;

1. Pull base image (this time ubuntu)
1. Install packages which are needed to build ruby
1. Clone [rbenv](https://github.com/sstephenson/rbenv)
1. Clone [ruby-build](https://github.com/sstephenson/ruby-build)
1. Install multiple versions of ruby which are defined at `versions.txt`
1. Install Bundler for each version

## Original Author

[tcnksm](https://twitter.com/deeeet)
