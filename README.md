# swift-statsd

Statsd Client Package for Swift

`swift-statsd` is a Swift package for sending metrics to a StatsD server. It's designed to be easy to use in any Swift application, providing a simple way to track and measure application performance and usage metrics.

## Features

- Supports all StatsD metrics types: counters, gauges, timers, and sets.
- Easy integration with Swift applications.
- Lightweight and efficient network usage.

## Installation

### Swift Package Manager

You can install `swift-statsd` using the [Swift Package Manager](https://swift.org/package-manager/) by adding the following dependency to your `Package.swift` file:

```swift
dependencies: [
    .package(url: "https://github.com/rogueethic/swift-statsd.git", from: "1.0.0")
]
```

## Usage

### Importing the Package

First, import StatsDPackage in your Swift file.

```swift
import StatsDPackage
```

Creating a StatsD Client

Create an instance of StatsDClient with the host and port of your StatsD server:

```swift
let statsDClient = StatsDClient(host: "your.statsd.host", port: 8125)
```

### Sending Metrics

Create and send different types of StatsD metrics:

Counter

```swift
let counterMetric = StatsDMetric(type: .counter, name: "example.counter", value: 1)
statsDClient.send(metric: counterMetric)
```

Gauge

```swift
let gaugeMetric = StatsDMetric(type: .gauge, name: "example.gauge", value: 100)
statsDClient.send(metric: gaugeMetric)
```

Timer

```swift
let timerMetric = StatsDMetric(type: .timer, name: "example.timer", value: 350)
statsDClient.send(metric: timerMetric)
```

Set

```swift
let setMetric = StatsDMetric(type: .set, name: "example.set", value: 4)
statsDClient.send(metric: setMetric)
```

## Contributing

Contributions are always welcome and greatly appreciated. If you have any suggestions for improvements or encounter any issues, please feel free to open an issue or submit a pull request.

## License

swift-statsd is released under the MIT License. See LICENSE for details.
