# WatchShaker
> Simple motion detector for ⌚️ (watchOS) shake gesture.

[![Swift Version][swift-image]][swift-url] [![Platform](https://img.shields.io/cocoapods/p/WatchShaker.svg?style=flat)](http://cocoadocs.org/docsets/WatchShaker)

<img src="https://raw.githubusercontent.com/ezefranca/WatchShaker/master/.utils/bwshaker.jpg" width="400" height="300" />

 WatchShaker is a watchOS helper to get your ⌚️ shake movements

## Requirements

- watchOS 6.0+
- Xcode 11.0+

## Installation

#### Manually
1. Download and drop ```WatchShaker.swift``` in your project to your watch target.  
2. Congratulations!  

## Usage example

```swift
import WatchKit
import Foundation


class InterfaceController: WKInterfaceController {

    override func awake(withContext context: Any?) {
        super.awake(withContext: context)
        // Configure interface objects here.
    }

    var shaker:WatchShaker = WatchShaker(shakeSensibility: .shakeSensibilityNormal, delay: 0.2)

    override func willActivate() {

        super.willActivate()
        shaker.delegate = self
        shaker.start()
    }

    override func didDeactivate() {

        super.didDeactivate()
        shaker.stop()

    }

}

extension InterfaceController: WatchShakerDelegate
{
    func watchShaker(_ watchShaker: WatchShaker, didShakeWith sensibility: ShakeSensibility) {
        print("I'm shook! ⌚️⌚️⌚️")
    }

    func watchShaker(_ watchShaker: WatchShaker, didFailWith error: Error) {
        print(error.localizedDescription)
    }
}

```

![](https://raw.githubusercontent.com/ezefranca/WatchShaker/master/.utils/applewatch.gif)

## Contribute

We would love for you to contribute to **WatchShaker**, check the ``LICENSE`` file for more info.

## Meta

Ezequiel França – [@ezefranca](https://twitter.com/ezefranca) and all awesome [Contributors](https://github.com/ezefranca/WatchShaker/graphs/contributors)

Distributed under the MIT license. See ``LICENSE`` for more information.

[swift-image]:https://img.shields.io/badge/swift-5.1-orange.svg
[swift-url]: https://swift.org/
[license-image]: https://img.shields.io/badge/License-MIT-blue.svg
[license-url]: LICENSE
[travis-image]: https://img.shields.io/travis/dbader/node-datadog-metrics/master.svg?style=flat-square
[travis-url]: https://travis-ci.org/dbader/node-datadog-metrics
[codebeat-image]: https://codebeat.co/badges/c19b47ea-2f9d-45df-8458-b2d952fe9dad
[codebeat-url]: https://codebeat.co/projects/github-com-vsouza-awesomeios-com
