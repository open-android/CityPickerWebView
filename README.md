
省市县三级联动，JS实现

![](http://upload-images.jianshu.io/upload_images/4037105-90cad9b81ae15e5f.gif?imageMogr2/auto-orient/strip)


* 更多干货请下载app


![黑马助手.png](http://upload-images.jianshu.io/upload_images/4037105-f777f1214328dcc4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


开源地址：[https://github.com/open-android/CityPickerWebView](https://github.com/open-android/CityPickerWebView)


简书：[http://www.jianshu.com/p/979983c6b0fe](http://www.jianshu.com/p/979983c6b0fe "地址")



## 使用步骤


### 1. 在project的build.gradle添加如下代码(如下图)

	allprojects {
	    repositories {
	        maven { url "https://jitpack.io" }
	    }
	}
![](http://upload-images.jianshu.io/upload_images/4037105-2faa5daca3bfe8a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### 2. 在Module的build.gradle添加依赖


      compile 'com.github.open-android:CityPickerWebView:0.1.0'


### 3.在Activity当中实现implements CityPickerListener监听器并且复制如下内容


        cityPicker = new CityPicker(MainActivity.this, this);
        findViewById(R.id.button).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                cityPicker.show();
            }
        });
        textView = (TextView) findViewById(R.id.textView);
        findViewById(R.id.button2).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                cityPicker.close();
            }
        });

	    @Override
	    public void getCity(final String name) {
	        textView.setText(name);
	    }
	
	    @Override
	    public void onBackPressed() {
	        if (cityPicker.isShow()){
	            cityPicker.close();
	            return;
	        }
	        super.onBackPressed();
	    }

详细的使用方法在DEMO里面都演示啦,如果你觉得这个库还不错,请赏我一颗star吧~~~

欢迎关注微信公众号

![](http://oi5nqn6ce.bkt.clouddn.com/itheima/booster/code/qrcode.png)
	


 

