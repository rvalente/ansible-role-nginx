# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

## [1.0] 2017-04-07
### Added
- Flag for SSL
- Sane/Secure Defaults for Nginx SSL as per https://cipherli.st/
- Expose dhparams private key size via `nginx_dhparam_keysize` var
- Default to Google Public DNS for SSL validation
- Gzip enabled by default
- SSL disabled by default
