## 1.Guide
This is a fork of [AC-QRCode-RN](https://github.com/MarnoDev/AC-QRCode-RN) , which is a useful QR code scanner component for React Native built on top of [react-native-camera](https://github.com/lwansbrough/react-native-camera) . But there are some bugs with React Native 0.50.0+ , and I have fixed it .


## 2.Features

- Can scan QR code,Bar code
- Support Android and iOS 
- Base on react-native-camera
- Scanning interface can be customized

## 3.Installation
```
// first step
npm install ac-qrcode --save

// second step
react-native link react-native-camera
```
## 4.Basic Usage
```
import { QRScannerView } from 'ac-qrcode';

export default class DefaultScreen extends Component {
    render() {
        return (

            < QRScannerView
                onScanResultReceived={this.barcodeReceived.bind(this)}

                renderTopBarView={() => this._renderTitleBar()}

                renderBottomMenuView={() => this._renderMenu()}
            />
        )
    }

    _renderTitleBar(){
        return(
            <Text
                style={{color:'white',textAlignVertical:'center', textAlign:'center',font:20,padding:12}}
            >Here is title bar</Text>
        );
    }

    _renderMenu() {
        return (
            <Text
                style={{color:'white',textAlignVertical:'center', textAlign:'center',font:20,padding:12}}
            >Here is bottom menu</Text>
        )
    }

    barcodeReceived(e) {
        Toast.show('Type: ' + e.type + '\nData: ' + e.data);
        //console.log(e)
    }
}
```
## 5.Props

![](https://github.com/ztMalone/react-native-qrcode-scanner/blob/master/screenshots/ac-qrcode-props.jpg)

|Prop|Type|Default|Optional|
|:--:|:--:|:--:|:--:|
|maskColor|string|#0000004D|true|
|borderColor|string|#000000|true|
|cornerColor|string|#000000|true|
|borderWidth|number|0|true|
|cornerBorderWidth|number|4|true|
|cornerBorderLength|number|20|true|
|rectHeight|number|200|true|
|rectWidth|number|200|true|
|isCornerOffset|bool|false|true|
|cornerOffsetSize|number|0|true|
|bottomMenuHeight|number|0|true|
|scanBarAnimateTime|number|2500|true|
|scanBarColor|string|#22ff00|true|
|scanBarImage|any|null|true|
|scanBarHeight|number|1.5|true|
|scanBarMargin|number|6|true|
|hintText|string|将二维码/条码放入框内，</br>即可自动扫描|true|
|hintTextStyle|object|{ color: '#fff', </br>fontSize: 14,</br>backgroundColor:'transparent'}|true|
|hintTextPosition|number|130|true|
|isShowScanBar|bool|true|true|
|bottomMenuStyle|object|-|true|
|renderTopBarView|func|-|flase|
|renderBottomMenuView|func|-|false|
|onScanResultReceived|func|-|false|

## 6.To Do

- [ ] Generate qr code
- [ ] Control flashlight

## 7.Thanks

- [react-native-camera](https://github.com/lwansbrough/react-native-camera)
- [react-native-qrcode](https://github.com/cssivision/react-native-qrcode)
- [react-native-qrcode-app](https://github.com/insiderdev/react-native-qrcode-app)