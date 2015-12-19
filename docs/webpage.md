<a name="Page"></a>
## Page
The Page object contains most of the functionality of PhantomJS and it is

**Kind**: global class  

* [Page](#Page)
    * _instance_
        * [.isClosed()](#Page+isClosed)
        * [.throwIfClosed()](#Page+throwIfClosed)
        * [.setFn(name, fn)](#Page+setFn)
        * [.get(name)](#Page+get)
        * [.set(name, value)](#Page+set)
        * [.evaluate(fn)](#Page+evaluate) ⇒ <code>object</code> &#124; <code>string</code> &#124; <code>number</code> &#124; <code>date</code>
        * [.addCookie(options)](#Page+addCookie)
        * [.clearCookies()](#Page+clearCookies)
        * [.close()](#Page+close)
        * [.deleteCookie(name)](#Page+deleteCookie)
        * [.getCookie(name)](#Page+getCookie)
        * [.evaluateJavaScript(javaScriptStr)](#Page+evaluateJavaScript)
        * [.evaluateAsync(fn)](#Page+evaluateAsync)
        * [.getPage(windowName)](#Page+getPage)
        * [.go()](#Page+go)
        * [.goBack()](#Page+goBack)
        * [.goForward()](#Page+goForward)
        * [.includeJs()](#Page+includeJs)
        * [.injectJs(filename)](#Page+injectJs)
        * [.open(url, methodOrSettings, data)](#Page+open)
        * [.openUrl(url, httpConf, settings)](#Page+openUrl)
        * [.reload()](#Page+reload)
        * [.render(filename, format, quality)](#Page+render)
        * [.renderBase64(format)](#Page+renderBase64)
        * [.sendEvent()](#Page+sendEvent)
        * [.setContent(content, url)](#Page+setContent)
        * [.stop()](#Page+stop)
        * [.switchToFocusedFrame()](#Page+switchToFocusedFrame)
        * [.switchToFrame()](#Page+switchToFrame)
        * [.switchToMainFrame()](#Page+switchToMainFrame)
        * [.switchToParentFrame()](#Page+switchToParentFrame)
        * [.uploadFile(selector, filename)](#Page+uploadFile)
        * [.clearMemoryCache()](#Page+clearMemoryCache)
        * [.renderPdf()](#Page+renderPdf)
        * [.renderHtml(htmlString, templateRenderDir)](#Page+renderHtml)
        * [.renderTemplate(template, templateRenderDir, options)](#Page+renderTemplate)
        * [.onAlert(handler)](#Page+onAlert)
        * [.onCallback(handler)](#Page+onCallback)
        * [.onClosing(handler)](#Page+onClosing)
        * [.onConfirm(handler)](#Page+onConfirm)
        * [.onConsoleMessage(handler)](#Page+onConsoleMessage)
        * [.onFilePicker(handler)](#Page+onFilePicker)
        * [.onInitialized(handler)](#Page+onInitialized)
        * [.onLoadFinished(handler)](#Page+onLoadFinished)
        * [.onLoadStarted(handler)](#Page+onLoadStarted)
        * [.onNavigationRequested(handler)](#Page+onNavigationRequested)
        * [.onPageCreated(handler)](#Page+onPageCreated)
        * [.onPrompt(handler)](#Page+onPrompt)
        * [.onResourceError(handler)](#Page+onResourceError)
        * [.onResourceReceived(handler)](#Page+onResourceReceived)
        * [.onResourceRequested(handler)](#Page+onResourceRequested)
        * [.onResourceTimeout(handler)](#Page+onResourceTimeout)
        * [.onUrlChanged(handler)](#Page+onUrlChanged)
    * _static_
        * [.readOnlyProperties](#Page.readOnlyProperties) : <code>Arrays(string)</code>
        * [.allowedSetProperties](#Page.allowedSetProperties) : <code>Array(string)</code>
        * [.allowedGetProperties](#Page.allowedGetProperties) : <code>Array(string)</code>
        * [.passProperties](#Page.passProperties) : <code>Array(string)</code>
        * [.base64Formats](#Page.base64Formats) : <code>Array(string)</code>
        * [.validRenders](#Page.validRenders) : <code>Array(string)</code>

<a name="Page+isClosed"></a>
### page.isClosed()
*Wrapper-specific*

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>Boolean</code>  
<a name="Page+throwIfClosed"></a>
### page.throwIfClosed()
*Wrapper-specific*

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+setFn"></a>
### page.setFn(name, fn)
*node-simple-phantom specific*

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | name of the event ('onConfirm', etc) |
| fn | <code>function</code> | handler of the event |

<a name="Page+get"></a>
### page.get(name)
*node-phantom-simple specific*

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | name of the property |

**Example**  
```js
page.set('paperSize.width', '50px')
```
<a name="Page+set"></a>
### page.set(name, value)
*node-phantom-simple specific*

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | name of the property |
| value | <code>anything</code> | value of the property |

**Example**  
```js
page.set('paperSize.width', '50px')
```
<a name="Page+evaluate"></a>
### page.evaluate(fn) ⇒ <code>object</code> &#124; <code>string</code> &#124; <code>number</code> &#124; <code>date</code>
[evaluate](http://phantomjs.org/api/webpage/method/evaluate.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | function to be evaluated |

<a name="Page+addCookie"></a>
### page.addCookie(options)
[addCookie](http://phantomjs.org/api/webpage/method/add-cookie.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>boolean</code> true if successful, false if not.  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| options | <code>object</code> |  |  |
| options.name | <code>string</code> |  | A valid cookie name |
| options.value | <code>string</code> |  | A cookie value |
| options.path | <code>string</code> |  | The path of the cookie |
| options.domain | <code>string</code> | <code>&quot;string&quot;</code> | The domain of the cookie |
| options.httponly | <code>boolean</code> | <code>false</code> | Whether to use HTTP only. |
| options.secure | <code>boolean</code> | <code>false</code> | Whether it should be secure or not |
| options.expires | <code>Number</code> |  | Number of miliseonds given                                                     with Date.now / Date.getTime                                                      it should be valid |

<a name="Page+clearCookies"></a>
### page.clearCookies()
[clearCookie](http://phantomjs.org/api/webpage/method/clear-cookies.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>boolean</code>  
<a name="Page+close"></a>
### page.close()
[close](http://phantomjs.org/api/webpage/method/close.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**:   
<a name="Page+deleteCookie"></a>
### page.deleteCookie(name)
[deletCookie](http://phantomjs.org/api/webpage/method/delete-cookie.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>boolean</code> true if successful, false if not.  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | Cookie name |

<a name="Page+getCookie"></a>
### page.getCookie(name)
*Wrapper Specific*

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>object</code> object of same type as can be found in `addCookie` documentation  

| Param | Type |
| --- | --- |
| name | <code>string</code> | 

<a name="Page+evaluateJavaScript"></a>
### page.evaluateJavaScript(javaScriptStr)
[evaluateJavaScript](http://phantomjs.org/api/webpage/method/evaluate-java-script.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type |
| --- | --- |
| javaScriptStr | <code>string</code> | 

<a name="Page+evaluateAsync"></a>
### page.evaluateAsync(fn)
[evaulateAsync](http://phantomjs.org/api/webpage/method/evaluate-async.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | Function to be evaluated |

<a name="Page+getPage"></a>
### page.getPage(windowName)
[getPage](http://phantomjs.org/api/webpage/method/get-page.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type |
| --- | --- |
| windowName | <code>string</code> | 

<a name="Page+go"></a>
### page.go()
[go](http://phantomjs.org/api/webpage/method/go.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+goBack"></a>
### page.goBack()
[goBack](http://phantomjs.org/api/webpage/method/go-back.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+goForward"></a>
### page.goForward()
[goForward](http://phantomjs.org/api/webpage/method/go-forward.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+includeJs"></a>
### page.includeJs()
[includeJs](http://phantomjs.org/api/webpage/method/include-js.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>string</code> url The url to retrieve the JS from  
<a name="Page+injectJs"></a>
### page.injectJs(filename)
[injectJs](http://phantomjs.org/api/webpage/method/inject-js.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>boolean</code> true if successful, false otherwise  

| Param | Type | Description |
| --- | --- | --- |
| filename | <code>string</code> | filename to inject |

<a name="Page+open"></a>
### page.open(url, methodOrSettings, data)
[open](http://phantomjs.org/api/webpage/method/open.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>string</code> status of the load, either 'success' or 'fail'  

| Param | Type | Description |
| --- | --- | --- |
| url | <code>string</code> | URL to do the request towards. Can be local file |
| methodOrSettings | <code>string</code> &#124; <code>object</code> | The method as a string or a settings object |
| settings.operation | <code>string</code> | The type of method - POST / GEt |
| settings.encoding | <code>encoding</code> | The encoding to use |
| settings.headers | <code>object</code> | An object with headers |
| settings.data | <code>string</code> | Stringified data (JSON etc) |
| data | <code>string</code> | Only used when methodOrSettings is a string |

<a name="Page+openUrl"></a>
### page.openUrl(url, httpConf, settings)
[openUrl](http://phantomjs.org/api/webpage/method/open-url.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type |
| --- | --- |
| url | <code>string</code> | 
| httpConf | <code>httpConf</code> | 
| settings | <code>settings</code> | 

<a name="Page+reload"></a>
### page.reload()
[reload](http://phantomjs.org/api/webpage/method/reload.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+render"></a>
### page.render(filename, format, quality)
[render](http://phantomjs.org/api/webpage/method/render.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| filename | <code>string</code> |  | Where to save the file. |
| format | <code>string</code> | <code>&quot;png&quot;</code> | If format is not specified, the file extension                             is extracted and used as the format. |
| quality | <code>number</code> | <code>100</code> | String or number value between 0 and 100 |

<a name="Page+renderBase64"></a>
### page.renderBase64(format)
[renderBase64](http://phantomjs.org/api/webpage/method/render-base64.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>string</code>            base64-encoded string  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| format | <code>string</code> | <code>&quot;png&quot;</code> | Either 'png', 'gif' or 'jpeg' |

<a name="Page+sendEvent"></a>
### page.sendEvent()
[sendEvent](http://phantomjs.org/api/webpage/method/send-event.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+setContent"></a>
### page.setContent(content, url)
[setContent](http://phantomjs.org/api/webpage/method/set-content.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| content | <code>string</code> | The HTML content of the webpage |
| url | <code>string</code> | The URL of the webpage |

<a name="Page+stop"></a>
### page.stop()
[stop](http://phantomjs.org/api/webpage/method/stop.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+switchToFocusedFrame"></a>
### page.switchToFocusedFrame()
[switchToFocusedFrame](http://phantomjs.org/api/webpage/method/switch-to-focused-frame.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+switchToFrame"></a>
### page.switchToFrame()
[switchToFrame](http://phantomjs.org/api/webpage/method/switch-to-frame.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+switchToMainFrame"></a>
### page.switchToMainFrame()
[switchToMainFrame](http://phantomjs.org/api/webpage/method/switch-to-main-frame.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+switchToParentFrame"></a>
### page.switchToParentFrame()
[switchToParentFrame](http://phantomjs.org/api/webpage/method/switch-to-parent-frame.html)

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+uploadFile"></a>
### page.uploadFile(selector, filename)
[uploadFile](http://phantomjs.org/api/webpage/method/upload-file.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type |
| --- | --- |
| selector | <code>string</code> | 
| filename | <code>string</code> | 

<a name="Page+clearMemoryCache"></a>
### page.clearMemoryCache()
*Developer Note*: There is little to no documentation on this function,

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+renderPdf"></a>
### page.renderPdf()
*Wrapper Specific*

**Kind**: instance method of <code>[Page](#Page)</code>  
<a name="Page+renderHtml"></a>
### page.renderHtml(htmlString, templateRenderDir)
*Wrapper Specific*

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>string</code>                   PDF  

| Param | Type | Description |
| --- | --- | --- |
| htmlString | <code>string</code> | the HTML string |
| templateRenderDir | <code>string</code> | directory to save the temp HTML file |

<a name="Page+renderTemplate"></a>
### page.renderTemplate(template, templateRenderDir, options)
*Wrapper Specific*

**Kind**: instance method of <code>[Page](#Page)</code>  
**Promise**: <code>string</code>                  PDF string  

| Param | Type | Description |
| --- | --- | --- |
| template | <code>object</code> | template object with a .render function |
| templateRenderDir | <code>string</code> | Where to render the html file |
| options | <code>object</code> | options that should be sent to the .render function |

<a name="Page+onAlert"></a>
### page.onAlert(handler)
[onAlert](http://phantomjs.org/api/webpage/handler/on-alert.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(message) {}` |

<a name="Page+onCallback"></a>
### page.onCallback(handler)
[onCallback](http://phantomjs.org/api/webpage/handler/on-callback.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(object) {}` |

<a name="Page+onClosing"></a>
### page.onClosing(handler)
[onClosing](http://phantomjs.org/api/webpage/handler/on-closing.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(closingPage) {}` |

<a name="Page+onConfirm"></a>
### page.onConfirm(handler)
[onConfirm](http://phantomjs.org/api/webpage/handler/on-confirm.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(message) {}` |

<a name="Page+onConsoleMessage"></a>
### page.onConsoleMessage(handler)
[onConsoleMessage](http://phantomjs.org/api/webpage/handler/on-console-message.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(message, lineNumber, sourceId) {}` |

<a name="Page+onFilePicker"></a>
### page.onFilePicker(handler)
[onFilePicker](http://phantomjs.org/api/webpage/handler/on-file-picker.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | Handler `function(oldFile) {}` |

<a name="Page+onInitialized"></a>
### page.onInitialized(handler)
[onInitialized](http://phantomjs.org/api/webpage/handler/on-initialized.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function() {}` |

<a name="Page+onLoadFinished"></a>
### page.onLoadFinished(handler)
[onLoadFinished](http://phantomjs.org/api/webpage/handler/on-load-finished.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(status) {}` |

<a name="Page+onLoadStarted"></a>
### page.onLoadStarted(handler)
[onLoadStarted](http://phantomjs.org/api/webpage/handler/on-load-started.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function() {}` |

<a name="Page+onNavigationRequested"></a>
### page.onNavigationRequested(handler)
[onNavigationRequested](http://phantomjs.org/api/webpage/handler/on-navigation-requested.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(url, type, willNavigate, main) {}` |

<a name="Page+onPageCreated"></a>
### page.onPageCreated(handler)
[onPageCreated](http://phantomjs.org/api/webpage/handler/on-page-created.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(newPage) {}` |

<a name="Page+onPrompt"></a>
### page.onPrompt(handler)
[onPrompt](http://phantomjs.org/api/webpage/handler/on-prompt.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(msg, defaultVal) {}` |

<a name="Page+onResourceError"></a>
### page.onResourceError(handler)
[onResourceError](http://phantomjs.org/api/webpage/handler/on-resource-error.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(resourceError) {}` |

<a name="Page+onResourceReceived"></a>
### page.onResourceReceived(handler)
[onResourceReceived](http://phantomjs.org/api/webpage/handler/on-resource-received.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(response) {}` |

<a name="Page+onResourceRequested"></a>
### page.onResourceRequested(handler)
[onResourceRequested](http://phantomjs.org/api/webpage/handler/on-resource-requested.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(requestData, networkRequest) {}` |

<a name="Page+onResourceTimeout"></a>
### page.onResourceTimeout(handler)
[onResourceTimeout](http://phantomjs.org/api/webpage/handler/on-resource-timeout.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(request) {}` |

<a name="Page+onUrlChanged"></a>
### page.onUrlChanged(handler)
[onUrlChanged](http://phantomjs.org/api/webpage/handler/on-url-changed.html)

**Kind**: instance method of <code>[Page](#Page)</code>  

| Param | Type | Description |
| --- | --- | --- |
| handler | <code>function</code> | `function(targetUrl) {}` |

<a name="Page.readOnlyProperties"></a>
### Page.readOnlyProperties : <code>Arrays(string)</code>
A list of settings that should not be sent through `set` as they are

**Kind**: static property of <code>[Page](#Page)</code>  
<a name="Page.allowedSetProperties"></a>
### Page.allowedSetProperties : <code>Array(string)</code>
A list of all the variables that can be used in .set function.

**Kind**: static property of <code>[Page](#Page)</code>  
**Todo**

- [ ] Add typecheck and check before sending the options to PhantomJS to optimize

<a name="Page.allowedGetProperties"></a>
### Page.allowedGetProperties : <code>Array(string)</code>
A list of all the variables that can be retrieved through .get

**Kind**: static property of <code>[Page](#Page)</code>  
<a name="Page.passProperties"></a>
### Page.passProperties : <code>Array(string)</code>
A list of settings that are undocumented in type and should therefore

**Kind**: static property of <code>[Page](#Page)</code>  
<a name="Page.base64Formats"></a>
### Page.base64Formats : <code>Array(string)</code>
A list of allowed formats for the base64 format

**Kind**: static property of <code>[Page](#Page)</code>  
<a name="Page.validRenders"></a>
### Page.validRenders : <code>Array(string)</code>
A list of allowed formats for the render function

**Kind**: static property of <code>[Page](#Page)</code>  