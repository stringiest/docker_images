FROM ruby:1.9.3

# The Debian Jessie APT packages have been archived.  Update where to
# find the packages.  If you don't do this you will get an error message
# like:
#
#  W: Failed to fetch http://http.debian.net/debian/dists/jessie-updates/InRelease
#
RUN sed -i '/jessie-updates/d' /etc/apt/sources.list

# Install stuff.  Currently just the build essentials.
RUN apt-get update -qq && apt-get install -y build-essential

# Install Gems.  
# Update the rubygems to prevent frozen string errors.
# Rubygems 2.7.8 is the latest version to support Ruby 1.9.3.
RUN gem install rubygems-update -v 2.7.8
RUN update_rubygems
RUN gem install bundler -v 1.15.0