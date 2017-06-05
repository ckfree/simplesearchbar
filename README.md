# SimpleSearchBar
精仿 IOS searchbar效果<br><br>
![example](https://github.com/ckfree/simplesearchbar/blob/master/device-2017-06-05-150817%20%5B320i%5D.gif)

## Quick start
### Step 1.<br> Add it in your root build.gradle at the end of repositories:

```
  allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
  ```
  ### Step 2.<br> Add the dependency:
  ```
  	dependencies {
	        compile 'com.github.ckfree:simplesearchbar:1.0'
	}
  ```
  
## Quick example:
### Step 1. 添加布局文件：
```
     <com.ckfree.common.SimpleSearchBar
        android:id="@+id/mysearchbar"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />
```
可定义如下自定义属性：<br>
```
    <com.ckfree.common.SimpleSearchBar
        android:id="@+id/mysearchbar"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:mCancelText="取消"
        app:mCancelTextColor="#123456"
        app:mCancelTextSize="14sp"
        app:mHintColor="#123456"
        app:mHintSize="13sp"
        app:mHintText="这里是Hint内容"
        app:mTextColor="#123456"
        app:mTextSize="13sp" />
```
### Step 2. 初始化控件：
```
     SimpleSearchBar mysearchbar = (SimpleSearchBar) findViewById(R.id.mysearchbar);
     View displayview = ...//跟随searchbar显示隐藏的view
     mysearchbar.init(displayview, new SimpleSearchBar.SearchBarWathcer() {
           @Override
           protected void _onTextChanged(String s) {
             //实时获取文字变更
           }
      });
```
