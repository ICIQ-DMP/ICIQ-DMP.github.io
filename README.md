# ICIQ-DMP.github.io
Contains the documentation of the DMP projects, mainly eChempad.

## Exhaustive list of the dependencies of the github 4 pages
Here are the dependencies of github 4 pages https://pages.github.com/versions/
Jekyll is 3.9.3

## Instructions for manual installation 

### dependencies
sudo apt-get install -y autoconf patch build-essential rustc libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libgmp-dev libncurses5-dev libffi-dev libgdbm6 libgdbm-dev libdb-dev uuid-dev  # use libgdbm5 if the 6 is not available

# rbenv ruby installation manager
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'eval "$(~/.rbenv/bin/rbenv init - bash)"' >> ~/.bashrc

# install ruby build as a rbenv plugin
git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build

# install ruby using rbenv
rbenv install -l  # List stable version
rbenv install 3.1.2  # install ruby version 3.1.2

# Install ruby gems
git clone https://github.com/rubygems/rubygems ~/.rubygems
cd ~/.rubygems  # dont know if this is the folder
rbenv global 3.1.2  # set ruby version
ruby setup.rb

# Install jekyll and bundler
gem install bundler -v "$(grep -A 1 "BUNDLED WITH" Gemfile.lock | tail -n 1)"
gem install jekyll



### Compile
cd ~/Desktop/ICIQ-DMP.github.io
`bundle install`

### Serve locally 
`bundle exec jekyll serve`

