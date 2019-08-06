# statuslayoutmanager
自用的页面状态显示布局

一、设置布局，点击view

```kotlin
mStatusLayoutManager = StatusLayoutManager.Builder(activity as Context)
		//设置正常显示布局
        .setContentLayout(getLayoutId())
		//设置数据为空时的布局
        .setEmptyLayout(R.layout.layout_status_layout_manager_empty)
		//设置异常时的布局
        .setErrorLayout(R.layout.layout_status_layout_manager_error)
		//设置加载时显示布局
        .setLoadingLayout(R.layout.layout_status_layout_manager_loading)
		//设置异常时点击的view ID
        .setErrorLayoutClickId(R.id.error_click)
		//设置空布局时点击的view ID
		.setEmptyLayoutClickId(R.id.empty_click)
        .newBuilder()
```

二、设置点击事件监听

```kotlin
 mStatusLayoutManager.setOnStatusLayoutClickListener(object: OnStatusLayoutClickListener{
            override fun onEmptyViewClick(view: View) {
    			TODO("空布局点击事件监听")
            }

            override fun onErrorViewClick(view: View) {
                TODO("异常布局点击事件") 
            }

        })
```

三、显示指定布局

```kotlin
//显示加载布局
mStatusLayoutManager.showLoading()
//显示内容布局
mStatusLayoutManager.showContent()
//显示空布局
mStatusLayoutManager.showEmptyLayout()
//显示异常布局
mStatusLayoutManager.showErrorLayout()
```

四、获取根布局 

```kotlin
mStatusLayoutManager.getRootLayout()
```

