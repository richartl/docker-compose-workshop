# build image
docker build -t docker/volume1 .

# run image
docker run -it -v "$PWD":/usr/src/app --name docker-volume1 docker/volume1

# check the difference between volume and copy

# create gemfile,lock with container quickly
docker run --rm -v "$PWD":/usr/src/app -w /usr/src/app ruby:2.5 bundle install

# run command without image
docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp ruby:2.5 ruby your-daemon-or-script.rb
