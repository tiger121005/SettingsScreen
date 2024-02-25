# SettingsScreen
![Language:Swift](https://img.shields.io/static/v1?label=Language&message=Swift&color=green&style=flat-square)
[![License](https://img.shields.io/github/license/KantaSwift/CustomTabBar)](https://github.com/KantaSwift/CustomTabBar/blob/main/LICENSE)
[![Twitter](https://img.shields.io/twitter/follow/KantaSwift?style=social)](https://twitter.com/kanta_Swift)

#### You can easily make a setting screen!!

## Table of Contents

- [Installation](#installation)
- [Basic Usage](#basic-usage)
- [Tab Style](#tab-style)
- [UpComing](#upcoming)
- [Contribution](#contribution)


## Installation

### Swift Package Manager 

#### Package

You can add this package to `Package.swift`, include it in your target dependencies.

```
let package = Package(
    dependencies: [
        .package(url: "https://github.com/KantaSwift/SettingsScreen.git", .upToNextMajor(from: "0.0.1")),
    ],
    targets: [
        .target(
            name: "<your-target-name>",
            dependencies: ["ScreenSettings"]),
    ]
)
```

#### Xcode

You can add this package on Xcode.
See [documentation](https://developer.apple.com/documentation/swift_packages/adding_package_dependencies_to_your_app).

#### Basic Usage

```swift
import SwiftUI
import SettingsNavigation

struct SettingsView: View {
    init() {}

    var body: some View {
        SettingsNavigationList {
            SettingsSection(title: "このアプリについて") {
                SettingsNavigationView(.assessment())
                SettingsNavigationView(.notification())
                SettingsNavigationView(.colorTheme())
                SettingsNavigationView(
                    .url(
                        .init(
                            title: "hoge",
                            url: "https://example.com"
                        )
                    )
                )
                SettingsNavigationView(
                    .custom(
                        .init(
                            title: "title",
                            action: {
                               // something
                            }
                        )
                    )
                )
            }
            .navigationTitle("設定")
            .navigationBarTitleDisplayMode(.inline)
        }
    }
}
```



