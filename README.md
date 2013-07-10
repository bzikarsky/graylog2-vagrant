graylog2-vagrant
================

An "easy" librarian-chef &amp; vagrant config for Graylog2 development 

## Requirements
- [Vagrant](http://www.vagrantup.com/)
- [librarian-chef](https://github.com/applicationsonline/librarian-chef)


## Usage

    git clone https://github.com/bzikarsky/graylog2-vagrant
    librarian-chef install
    vagrant up

By default port 12201 UDP is forwarded and listening for GELF-messages. Test with:

    echo '{
    "host": "localhost", 
    "version": "1.0", 
    "facility": "cmd-testing", 
    "short_message": "Testing!"
    }' | nc -u 127.0.0.1 12201
    
The Web-UI listens on [localhost:8080](http://localhost:8080).
