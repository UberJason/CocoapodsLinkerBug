# CocoapodsLinkerBug

This project demonstrates an issue with Cocoapods 1.6.1. The project structure contains:
- a main iOS app target, "CocoapodsLinkerBug"
- a Today extension, "Today"
- a shared framework, "MyAwesomeKit"

There's a single Cocoapod dependency that `MyAwesomeKit` has, but which the iOS app target and the Today extension do _not_ have.

With Cocoapods 1.5.3, running `pod install` sets everything up correctly, and the app runs.
With Cocoapods 1.6.1, we get an error:

    dyld: Library not loaded: @rpath/Ensembles.framework/Ensembles
      Referenced from: /Users/Jason/Library/Developer/Xcode/DerivedData/CocoapodsLinkerBug-ckjfrdjtthboxzbxdumgajtwmszz/Build/Products/Debug-iphonesimulator/MyAwesomeKit.framework/MyAwesomeKit
      Reason: image not found

It's interesting to note that the Today widget doesn't even have to have any dependencies - simply referencing it in the Podfile at all triggers the error.
