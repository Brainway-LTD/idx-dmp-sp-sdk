# IdxDmpSdk

## Integration DataManagerProvider example

```swift
class ViewController: UIViewController {
    var dmp: DataManagerProvider?
    
    ...

    override func viewDidLoad() {
        super.viewDidLoad()

        self.dmp = DataManagerProvider(providerId: providerId, monitoringLabel: "My app name") {_ in
          // Success callback
        }
    }

    ...
    
    @IBAction func handleShowAd() {
        guard let dmp = self.dmp else {
            return
        }

        let adRequest: GAMRequest = GAMRequest()
        adRequest.customTargeting = dmp.getCustomAdTargeting()
    }

    ...
}
```

## Integration DMPWebViewConnector example

```swift
class ViewController: UIViewController {
    var dmpWebViewConnector: DMPWebViewConnector?
    
    ...

    override func viewDidLoad() {
        super.viewDidLoad()
        // You have to set your WKWebView instance
        connector = DMPWebViewConnector(yourWebView.configuration.userContentController)
    }

    ...
    
    @IBAction func handleShowAd() {
        guard let connector = self.connector else {
            return
        }

        let adRequest: GAMRequest = GAMRequest()
        adRequest.customTargeting = connector.getCustomAdTargeting()
    }

    ...
}
```

## Author

Brainway LTD, https://brainway.co.il/

## License

IdxDmpSdk is available under the MIT license. See the LICENSE file for more info.