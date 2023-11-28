# libbase58-podspec

A libbase58.podspec file for [libbase58](https://cocoapods.org/pods/libbase58) pod

## Guides and related resources
* [Getting setup with Trunk](https://guides.cocoapods.org/making/getting-setup-with-trunk.html)
* [Update an existing Pod](https://guides.cocoapods.org/making/specs-and-specs-repo.html#how-do-i-update-an-existing-pod)

## General pod information
Gt the pod information
```
pod trunk info libbase58
```

## Validate
Check the generated result podspec.json file:
```
pod ipc spec libbase58.podspec > libbase58.podspec.json
```
Compare with the original if necessary: [libbase58.podspec.json](https://github.com/CocoaPods/Specs/blob/master/Specs/3/4/3/libbase58/0.1.4/libbase58.podspec.json)

Pass validation using lint:
```
pod spec lint libbase58.podspec --verbose
```

## Publish
Submit Podspec to Trunk:
```
pod trunk push libbase58.podspec
```

If the same version already exists, there will be an error like: `[!] Unable to accept duplicate entry for: libbase58 (0.1.4)`. 
since change affects only the contents of the podspec but not the underlying library, it is possible to
1. delete the pod
```
$ pod trunk delete libbase58 0.1.4

WARNING: It is generally considered bad behavior to remove versions of a Pod that others are depending on!
Please consider using the `deprecate` command instead.
Are you sure you want to delete this Pod version?
> yes
...
```
2 and then re-push it:
```
$ pod trunk push libbase58.podspec

Validating podspec
 -> libbase58 (0.1.4)
    - NOTE  | xcodebuild:  note: Using codesigning identity override: -
    - NOTE  | xcodebuild:  note: Building targets in dependency order
    - NOTE  | xcodebuild:  note: Using codesigning identity override:

Updating spec repo `trunk`

CocoaPods 1.14.3 is available.
To update use: `sudo gem install cocoapods`

For more information, see https://blog.cocoapods.org and the CHANGELOG for this version at https://github.com/CocoaPods/CocoaPods/releases/tag/1.14.3


--------------------------------------------------------------------------------
 🎉  Congrats

 🚀  libbase58 (0.1.4) successfully published
 📅  March 21st, 2017 00:07
 🌎  https://cocoapods.org/pods/libbase58
 👍  Tell your friends!
--------------------------------------------------------------------------------
```