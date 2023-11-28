# libbase58-podspec

A libbase58.podspec file for CocoaPods

## Guides and related resources
* [Getting setup with Trunk
](https://guides.cocoapods.org/making/getting-setup-with-trunk.html)
* [Update an existing Pod](https://guides.cocoapods.org/making/specs-and-specs-repo.html#how-do-i-update-an-existing-pod)

## General pod information
Gt the pod information
```
$ pod trunk info libbase58
```

## Validate
Check the generated result podspec.json file:
```
$ pod ipc spec libbase58.podspec > libbase58.podspec.json
```
Compare with the original if necessary: [libbase58.podspec.json](https://github.com/CocoaPods/Specs/blob/master/Specs/3/4/3/libbase58/0.1.4/libbase58.podspec.json)

Pass validation using lint:
```
$ pod spec lint libbase58.podspec --verbose
```

## Publish
Submit Podspec to Trunk:

```
$ pod trunk push libbase58.podspec
```
