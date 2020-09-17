# ASAudioWaveformView

[![CI Status](https://img.shields.io/travis/Andrew Shen/ASAudioWaveformView.svg?style=flat)](https://travis-ci.org/Andrew Shen/ASAudioWaveformView)
[![Version](https://img.shields.io/cocoapods/v/ASAudioWaveformView.svg?style=flat)](https://cocoapods.org/pods/ASAudioWaveformView)
[![License](https://img.shields.io/cocoapods/l/ASAudioWaveformView.svg?style=flat)](https://cocoapods.org/pods/ASAudioWaveformView)
[![Platform](https://img.shields.io/cocoapods/p/ASAudioWaveformView.svg?style=flat)](https://cocoapods.org/pods/ASAudioWaveformView)

![screenshop](./screenshot.png)

![zoom](./zoom1.gif)
## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements
swift 5.0

## Installation

ASAudioWaveformView is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'ASAudioWaveformView'
```

## Usage
### there are two ways to create waveform view, waveform will adjust to fit the frame automatically
1. init with frame

    ```swift
    let wave = ASAudioWaveformView.create(frame: CGRect(x: 0, y: 40, width: 200, height: 100)) { (config) in
        let url = Bundle.main.url(forResource: "test", withExtension: "mp3")
        config.audioURL(url).maxPointsCount(500).fillColor(.systemTeal)
    }
    ```
2. if you use Autolayout or set the frame later

    ```swift
    let wave = ASAudioWaveformView()
    wave.createWaveform { (config) in
            let url = Bundle.main.url(forResource: "test", withExtension: "mp3")
            config.audioURL(url).positionType(.top).fillColor(.green)
    }
    ```

#### config waveform
```
    /// config waveform postion, the default is center
    public func positionType(_ type: ASAudioWaveformView.PositionType) -> ASAudioWaveformConfig

    /// config waveform content style, the default is polyline
    public func contentType(_ type: ASAudioWaveformView.ContentType) -> ASAudioWaveformConfig

    /// config waveform fill color, the default is yellow
    public func fillColor(_ color: UIColor) -> ASAudioWaveformConfig

    /// config waveform audio source
    public func audioURL(_ URL: URL?) -> ASAudioWaveformConfig

    /// config max samples count, the default is 1000
    public func maxPointsCount(_ count: Int) -> ASAudioWaveformConfig
```

### reload with different audio URL
waveform will adjust to fit the frame automatically

```
/// Refresh waveform by audio url
public func refreshWaveform(with audioURL: URL?)
```


## Author

Andrew Shen, iandrew@126.com

## License

ASAudioWaveformView is available under the MIT license. See the LICENSE file for more info.