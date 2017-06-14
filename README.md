##  关于使用jQuery前端上传文件

> 我们都知道 html中file类型的input可以直接读取本地的文件;
> 如果使用form表单的话，那么action = url 这就会上传完文件会刷新页面，返回值就会显示在页面区域，显然这并不是我们想要的。
> 所以要再用 ajax 技术，采用无刷新的上传文件。

##### 代码如下：

###### html
``` xml 
<body>
     <input type="file" name="upfile" id="upfile"/>
     <input id="uploadBtn" type="submit" value="开始上传" />
     
     //引入jquery库
     <script src="../js/jquery-1.10.1.min.js"></script>
</body>


```
###### js
```js
    var url = "http://192.168.100.151:7001/GDPaymentCenterServer_FromService/UploadFileServlet.do";
    
    $('#uploadBtn').on('tap', function(){
    
    	    fd.append("paragram", 12345); //上传的参数名 参数值 k-v键值对
   		    fd.append("upfile", $("#upfile").get(0).files[0]);//上传的文件file
            $.ajax({
                 url: url,
                 type: "POST",
                 processData: false,
                 contentType: false,
                 data: fd,
                 success: function(data) {
				 	console.log(data);
                 }
            })
    })
			


```
