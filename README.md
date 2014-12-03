#JHProgressHUD

JHProgressHUD is an iOS class written in Swift to display a translucent HUD with an indicator and/or labels while work is being done in a background thread. The HUD is meant as a replacement for the private UIKit UIProgressHUD.

## Adding MBProgressHUD to your project

### Source Files

Add the `JHProgressHUD.swift` file to your project.

1. [Download the latest code version](https://github.com/harikrishnant1991/JHProgressHUD/archive/master.zip) or add the repository as a git submodule to your git-tracked project.
2. Open your project in Xcode, then drag and drop `JHProgressHUD.swift` onto your project (use the "Product Navigator view"). Make sure to select Copy items when asked if you extracted the code archive outside of your project.

## Usage

The `JHProgressHUD` is a singleton class and has only a single instance throughout the project. That is you see the same HUD added to multiple views. As a result, HUD duplication doesn't happen. You can use the following code to access the instance of `JHProgressHUD` anywhere inside the project.

```Swift
JHProgressHUD.sharedHUD
```

To show the HUD added to a view, with a title and footer text, use the following code:

```Swift
JHProgressHUD.sharedHUD.showInView(self.view, withHeader: "Loading", andFooter: "Please Wait")
```

To show the HUD added to a window, with a title and footer text, use the following code:

```Swift
JHProgressHUD.sharedHUD.showInWindow(aWindow, withHeader: "Loading", andFooter: "Please Wait")
```

To show the HUD without any header and footer text added to a view:

```Swift
JHProgressHUD.sharedHUD.showInView(self.view)
```

To show the HUD without any header and footer text added to a window:

```Swift
JHProgressHUD.sharedHUD.showInWindow(self.view)
```

To hide the loader, you can call the following function from any class. The HUD will be removed from any view it is shown in:

```Swift
JHProgressHUD.sharedHUD.hide()
```

The HUD might not show if you try to display the loader in a `ViewController`'s `viewDidLoad()` method, since adding subviews maynot always work in the `viewDidLoad()`. It is prefered to show the HUD at least only after the `viewWillAppear()` is called. The HUD blocks the user interaction in the underlying view or window once it is shown, till it is hidden.

## License

This code is distributed under the terms and conditions of the [MIT license](https://github.com/harikrishnant1991/JHProgressHUD/blob/master/LICENSE).