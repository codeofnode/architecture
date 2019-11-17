# branching
Branch tree for the repo

```text
master (latest version passed by QA, passing integration tests, ideal branch = runner highest of v[*])
  |
  |-- v0 (version 0.x.x, ideal branch = runner highest of v0.[*])
  |   |
  |   |--v0.0(version 0.0.x, ideal branch = runner highest of v0.0.[*])
  |   |   |
  |   |   |-- v0.0.0 (latest version passed by devs, passing all unit tests)
  |   |   |   |
  |   |   |   | -- v0.0.0-1 (addressing issue/task 1 in v0.0.0)
  |   |   
  |   |--v0.1(version 0.1.x, ideal branch = runner highest of v0.1.[*])
  |   |   |
  |   |   |-- v0.1.0
  |   |   |   |
  |   |   |   | -- v0.1.0-3 (addressing issue/task 3 in v0.1.0)
```

# How to start for a project
- Create a repo in git host, add readme, licsense, gitignore, todo, changelog 
- Clone to local
- have a working poc on master itself, try with single commit (sqaush before pushing)
- Push to origin
- Create a issue (no1) in githost, eg the feature 1
- create 4 more branches: v0, v0.0, v0.0.0, v0.0.0-1 as per above structure
- after feature 1 is ready, start with creating changelog, fill below
- change the version in package.json
- push to v0.0.0-1 and raise PR from v0.0.0-1 to v0.0.0, merge the pr
- create another issue (no2) in project eg bug fix of feature 1
- fork from v0.0.0 as v0.0.0-2, raise pr to v0.0.0, merge the pr
- for any feature or bug, always fork from a vX.X.X branch, not master or any other kind of branch


# changelog

```text
# changelog
Changes across the versions

## [0.1.3]  - 2019-04-19
### Added
- Some feature

### Fixed
- Fix 1


## [0.0.0]  - 2019-02-19
### Added
- Started the project

### Fixed
- No fixes


  [0.1.3]: https://github.com/codeofnode/projectname/pull/{{pull_req_no_for_v0.1.3}}
  [0.0.0]: https://github.com/codeofnode/projectname/pull/{{pull_req_no_for_v0.0.0}}
```

# todo
```text
# TODO
All todos will be noted in this file, with ref to the issue id

## [0.1.3]  - 2019-04-19
### To Be Added
- [0.1.3-4] Some feature with issue id 4

### To be Fixed
- [0.1.3-2] Fix 1 of feature x


## [0.2.3]  - 2019-7-19
### To Be Added
- [0.2.3-9] Some feature 2

### To be Fixed
- [0.2.3-8] some fix of feature x


  [0.1.3]: https://github.com/codeofnode/projectname/tree/v0.1.3
  [0.1.3-2]: https://github.com/codeofnode/projectname/issues/2
  [0.1.3-4]: https://github.com/codeofnode/projectname/issues/4
  
  [0.2.3]: https://github.com/codeofnode/projectname/tree/v0.2.3
  [0.2.3-8]: https://github.com/codeofnode/projectname/issues/8
  [0.2.3-9]: https://github.com/codeofnode/projectname/issues/9
  
```
