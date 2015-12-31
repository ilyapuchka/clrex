# clrex
Simple script to generate colors factory methods from clr files

This basic script will help to generate UIColor factory methods from you system colors palattes.
Inspired by [this tip](http://natashatherobot.com/xcode-color-palette/) by [@natashatherobot](https://twitter.com/natashatherobot) and [ColorTools](https://github.com/ramonpoca/ColorTools).

# Usage

To use this script in your project download `clrex.swift`, put it somewhere in your project 
and add new "Run Script" phase before "Compile Source":

```
xcrun swift -sdk $(xcrun --show-sdk-path --sdk macosx) ./clrex.swift
```

In this example `clrex.swift` was copied into source root folder of the project.
Generated file will be created in the same folder where you put `clrex.swift`

# Example

Script will generate file called `Colors.generated.swift` that will look like this

```swift
enum MyColors {

  static func blackColor() -> UIColor {
    return UIColor(red: 0.000000, green: 0.000000, blue: 0.000000, alpha: 1.000000)
  }

  static func grayColor() -> UIColor {
    return UIColor(red: 0.265146, green: 0.265153, blue: 0.265149, alpha: 1.000000)
  }

}

```

Script will generate enum for each `*.clr` file in `~/Library/Colors/` named by the name of the file. 
Functions will be named by the names of colors in those palettes with removed spaces and some additional formatting.

# License
clrex.swift is created by [Ilya Puchka](https://twitter.com/ilyapuchka) and released under a MIT License.
