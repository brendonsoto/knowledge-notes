---
aliases: 
created: 2022-03-10, 7:11:51 pm (Thursday, March 10th)
updated: 2022-03-11, 9:50:02 am (Friday, March 11th)
---
This is kind of a dump of info related to [concourse CI](https://concourse-ci.org)

## Resources
- info on the [registry-image-resource](https://github.com/concourse/registry-image-resource)
- [oci-build-task](https://github.com/concourse/oci-build-task)
    - what is OCI? [Open Container Initiative](https://opencontainers.org/)
        - [spec](https://github.com/opencontainers/image-spec)

## How to...
Validate a pipeline:
`fly validate-pipeline -c ./path/to/config.yml`

Update a pipeline:
`fly -t <name-space> sp -p <repo-and-specific-pipeline> -c ./path/to/config.yml`

## General
You have *three* main groups of *configurations*:
- `resource_types`: definitions of non-standard resources
    - [docs](https://concourse-ci.org/resource-types.html)
    - [list of standard resources](https://resource-types.concourse-ci.org/)
- `resources`: tools to carry out jobs
- `jobs`: instruction sets for tasks

`jobs` is where to go to find out how something is being done.
A `job` relies on one or multiple `resources`.
For example, fetching a *repo* can be a `resource`.
Concourse comes with many [resources](https://resource-types.concourse-ci.org/) to begin with but sometimes you may need to make your own.
This is where `resource_types` come in.
You can define a `resource` here using other resources.
An example of this could be a resource someone has created like this resource to work with [github pull requests](https://github.com/telia-oss/github-pr-resource).

## Gotchas / Quirks / Things that I wish I knew before
### Tags
https://concourse-ci.org/tags-step.html

Helps give a name to refer to a configuration from another configuration
This way you can have multiple versions of a similar config but that vary slightly, like version number of a language.


### Changing the image used by a task
A task/config can have a sort of **default image** set by using `image_resource` ([docs](https://concourse-ci.org/tasks.html#schema.task-config.image_resource)).
To **override** an image that a task uses, use the `image` property.

Example:
```yaml
- task: do the thing
  file: repo/path/to/file/with/image/already/set.yml
  image: resource-with-specific-version-of-dep
  attempts: 3
```

Another doc regarding [image in the task config](https://concourse-ci.org/task-step.html#schema.task.image).