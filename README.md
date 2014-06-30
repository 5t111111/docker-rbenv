# Dorker rbenv

Prepare image which is installed muliple versions of ruby and bundler for each versions. 

## Usage

You can use this image for your project soon. It's uploaded docker.io, [5t111111/rbenv](https://index.docker.io/u/5t111111/rbenv/).

```
docker pull 5t111111/rbenv
```

or in Dockerfile

```
FROM 5t111111/rbenv
```

Run it !

```
docker run -i -t 5t111111/rbenv bash -l -c 'rbenv global 2.1.2; bundle ...'
```


## Build rbenv image

Install multiple versions of ruby by [rbenv](https://github.com/sstephenson/rbenv). you can define ruby verion which you want to use in `versions.txt`.


### Build image

```
docker build -t TAG .
```

Dockerfile execute belows;

1. Pull base image (this time ubuntu)
2. Install packages which are needed to build ruby
3. Clone [rbenv](https://github.com/sstephenson/rbenv)
4. Clone [ruby-build](https://github.com/sstephenson/ruby-build)
5. Install multiple versions of ruby which are defined at `versions.txt`
6. Install Bundler for each version

## Original Author

[tcnksm](https://twitter.com/deeeet)
