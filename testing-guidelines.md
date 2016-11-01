---
layout: page
title: Testing Guidelines
permalink: /testing-guidelines/
---

There are basically two types of Cloudify Examples - plugins and blueprints. Each require various types of tests.

# Plugins

Tools:

* Flake8 - We use Flake8 to enforce some basic style guidelines.
* Nosetests - We use Nose to run all unit tests & coverage to estimate code coverage.

Approach:

* Unit tests should test Cloudify workflow operations.
* Use the Cloudify Mock Contexts provided in Cloudify Plugins Common. (import cloudify.mocks)
* Workflow tests can be used to test an entire blueprint with the plugin. (from cloudify.test_utils import workflow_test)
* Minimum 90% coverage.


# Blueprints

Approach:

* Certainly all blueprints should have been tested manually and pass basic validation. (cfy blueprints validate)
* All scripts should be unit tested as much as possible, like a regular plugin.
* Finally, there should detailed documentation of the conditions under which the blueprint is known to work, including all versions of the IaaS, Cloudify, dependent software, etc.
