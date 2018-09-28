[![Build Status](https://travis-ci.com/modoolar/vault.svg?branch=11.0)](https://travis-ci.com/modoolar/vault)
[![codecov](https://codecov.io/gh/modoolar/vault/branch/11.0/graph/badge.svg)](https://codecov.io/gh/modoolar/vault)

Repository for Vault related modules.
========================================

This module uses encrypted fields to store sensitive credentials, and
        related information.
        
Requirements
=============
    pip install cryptography
        
Configuration
=============
In order for encrypted vault to work, please pass following configuration options to odoo:
`encryption_key` - this is utf-8 encoded AES key, It could be generated like this:
    
    from cryptography.fernet import Fernet
    Fernet.generate_key().decode() 

Also you must add `base_encrypted_field` module to `server_wide_modules` configuration parameter (don't exclude web)
    
    server_wide_modules = web,base_encrypted_field