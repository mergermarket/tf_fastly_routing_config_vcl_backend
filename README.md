# tf\_fastly\_routing\_config\_vcl\_backend terraform module

[![Build Status](https://travis-ci.org/mergermarket/tf_fastly_routing_config_vcl_backend.svg?branch=master)](https://travis-ci.org/mergermarket/tf_fastly_routing_config_vcl_backend)

This module is for generating Fastly routing config for inclusion in a custom
VCL file. This is mainly useful for use building up the `custom_vcl_backends`
parameters to [tf\_fastly\_frontend](https://github.com/mergermarket/tf_fastly_frontend)
(these allow for a variable number of backends to be supplied via a parameter -
something that isn't currently possible in ordinary terraform).

## Interface

To see all the input variables and outputs see `variables.tf` and `outputs.tf`.
The required input variables are:

* `backend_name` - the name of the backend (must be unique across backends).
* `backend_host` - the host to connect to (https default port 443).

The outputs are:

* `vcl_backend` - fragment of VCL to add to custom\_vcl\_backends`.
