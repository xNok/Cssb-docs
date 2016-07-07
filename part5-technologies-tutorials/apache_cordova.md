# Apache Cordova

This documentation sheet, put together a lot of interesting things about mobile app developement using apache cordova. You can found most of these trick into Cssb.

## Start with apache cordova

* [Official website](https://cordova.apache.org/)

## Tricks

### Interact with the keyboard

One of the most disturbing issue is to let the focused element on screen when the keyboar appear.

The easiest solution is get back to basics. What happend when the keyboard appear? The body of your app is resize, so catch this and scroll to the desire element.desire

Requirement :
* [JQuery](https://jquery.com/)
* [jquery.scrollhttps://jquery.com/To plugin](https://github.com/flesler/jquery.scrollTo)

``` javascript
function onResize(){
  console.log("[INFO] body resised");

  var el = $(document.activeElement);
  var offset = -$(".scrollerWrap").height() + $(el).outerHeight() + 5px;
  $(".scrollerWrap").scrollTo(el,{offset: offset});
  console.log("[INFO] scrollTo");
}
```

``` html
<body onresize="onResize()">
    ...
</body>
```

### Plugins

* [PhoneGap Plugin BarcodeScanner](https://github.com/phonegap/phonegap-plugin-barcodescanner)

Totaly fonctional and easy to implement cross-platform BarcodeScanner for Cordova / PhoneGap.

> cordova plugin add cordova-plugin-network-information

* [cordova plugin network information](https://github.com/phonegap/phonegap-plugin-barcodescanner)

Essential if you need to use the network

> cordova plugin add cordova-plugin-network-information

``` javascript
function checkConnection() {
    var networkState = navigator.connection.type;

    var states = {};
    states[Connection.UNKNOWN]  = 'Unknown connection';
    states[Connection.ETHERNET] = 'Ethernet connection';
    states[Connection.WIFI]     = 'WiFi connection';
    states[Connection.CELL_2G]  = 'Cell 2G connection';
    states[Connection.CELL_3G]  = 'Cell 3G connection';
    states[Connection.CELL_4G]  = 'Cell 4G connection';
    states[Connection.CELL]     = 'Cell generic connection';
    states[Connection.NONE]     = 'No network connection';

    alert('Connection type: ' + states[networkState]);
}

checkConnection();
```
