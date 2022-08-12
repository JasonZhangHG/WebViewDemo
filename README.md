# WebViewDemo
WebViewDemo 

WebView加载时解决Loading闪烁问题
一般移动端加载H5时需要点时间，所以这个时候经常加个Loading。

常规的做法：

1.在webview刚开始的时候showloading,等WebViewClient回调onPageFinished的时候hide loading,

2.Webview先setWebViewClient(mWebClient),在WebViewClient的 onPageStarted()回调中show loading 在onPageFinished()中hide loading 

以上的做法正常情况下都没有问题，但是一旦遇到加载的网页中出现重定向的时候onPageStarted()和onPageFinished() 会走多次，这个时候就会出现loading 闪烁问题

解决办法：其实在onPageFinished()的回调中可以通过webview拿到当前的progress,根据progress的进度来决定是否隐藏loading 

https://user-images.githubusercontent.com/22411415/184279416-097f6aaa-92e7-4897-907c-e347f831d4dd.mp4

csdn文章地址：

