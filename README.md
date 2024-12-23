# **SafeKeyboard**
Android自定义安全软键盘，完全自定义，方便、安全、可靠

下一步计划：增加换肤、打包发布等功能

详见:  [Android 自定义安全软键盘 SafeKeyboard 开发详细说明 2.0](https://github.com/SValence/SafeKeyboard/wiki/SafeKeyboard-2.0)

预览<br>
![image](explain_files/SafeKeyboard_preview_1.5x.gif)

## **历史更新**

### 十二、 2024/11/28
* 1 . [修改] 修改 `SafeKeyboard` 类型返回错误导致无法输入的 `BUG`.
* 2 . [修改] 修改 部分代码.
* 3 . [修改] 待支持 `WebView` 中调用, 不过目前没有太好的办法, 因为还没找到 `html` 页面的输入框获得焦点时禁止系统弹出软键盘的方法, 有机会再完善. 见 [`issue#21`](https://github.com/SValence/SafeKeyboard/issues/21)
* 4 . [展望] 待新增加密功能。 见 [`issue#28`](https://github.com/SValence/SafeKeyboard/issues/28)

### 十一、 2024/11/05
* 1 . [修改] 修改 `SafeKeyboard` 字母、数字、符号键盘无法相互切换的 `BUG`.
* 2 . [修改] 修改 有 `EditText` 未使用 `SafeKeyboard` 且其 `IME_ACTION` 被设置为 `EditorInfo.IME_ACTION_NEXT` (下一项) 的处理逻辑. 允许这样使用.
* 3 . [修改] 修改 `SafeKeyboard` 各键盘显示、切换的处理逻辑, 相同 `EditText` 中各键盘切换、不同 `EditText` 中各键盘切换, 各自独立处理, 互不干扰.
* 4 . [修改] 修改 `SafeKeyboard` 显示(指的是由未显示 `->` 显示)逻辑, 焦点变化显示、隐藏后再次点击显示, 各自独立处理, 互不干扰.
* 5 . [修改] 修改 部分代码冗余问题, 优化部分执行逻辑.
* 6 . [展望] 待新增加密功能。 见 [`issue#28`](https://github.com/SValence/SafeKeyboard/issues/28)

### 十、 2024/11/04
* 1 . [新增] 新增 `SafeKeyboard` 支持给按键自定义背景和字体颜色见 [`issue#31`](https://github.com/SValence/SafeKeyboard/issues/31)
* 2 . [新增] 新增 `SafeKeyboard` 取消输入功能, 当用户抬起手指时的位置已不在按下去的按键范围内时, 取消本次输入. 该功能可设置开启关闭, 默认开启.
* 3 . [修改] 修改 部分代码冗余问题, 重命名部分文件.

### 九、 2024/10/28
* 1 . [修改] 修改 `SafeKeyboard` 字母键盘开启随机显示功能后, 切换大小写时字母显示错误等问题。 见 [`issue#30`](https://github.com/SValence/SafeKeyboard/issues/30)
* 2 . [修改] 修改 部分代码冗余问题.
* 3 . [展望] 待增加键盘字体颜色配置。 见 [`issue#31`](https://github.com/SValence/SafeKeyboard/issues/31)

### 八、 2022/04/13
* 1 . [修改] 修改 `SafeKeyboard` 使用 `EditText.getId()` 作为唯一 `key` 确定 `EditText` 可能会出现系统键盘和 `SafeKeyboard` 同时出现的 `BUG`。
             即： `include` 多次复用同一个布局文件, 存在某个引入的布局文件没有使用 `SafeKeyboard` 时, 会出现该问题。 见 `issue#23`
* 2 . [修改] 修改 部分代码冗余问题.

### 七、 2022/04/12
* 1 . [修改] 修改 SafeKeyboard 无法按键震动的问题, 并优化震动开启逻辑
* 2 . [修改] 修改 未使用 `SafeKeyboard` 的 `EditText imeOption` 被设置为 "下一项" 时, 点击此按键可能会导致系统软件盘和 `SafeKeyboard` 软键盘同时显示的 `BUG`.
* 3 . [修改] 修改 `SafeKeyboard aar` 的命名方式, 确定版本号格式

### 六、 2022/04/11
* 1 . [新增] 新增 `SafeKeyboardConfig` 属性, 所有的键盘配置都在这里个对象里定义, 底层所有可在代码层修改的配置均在 `SafeKeyboardConfig` 中提供配置接口, 详细参考 `MainActivity`
* 2 . [修改] 修改 `SafeKeyboard` 字母随机功能, 修复上个更新无法切换大小写的问题, 并修改大写未锁定时输入一个大写字母后切换为小写字母时又重复刷新字母位置的问题
* 3 . [适配] 适配 `SafeKeyboard` 可设置每个 `EditText` 是否开启按键震动

### 五、 2022/04/08
* 1 . [修改] 修改 `SafeKeyboard` 为 `Library` (待提供接口以供上层修改必要数据)
* 2 . [适配] 适配 `AndroidX`
* 3 . [新增] 新增 字母键盘随机显示功能, 并修改开启随机的方式, 不直接在 `SafeKeyboardView` 中设置相关属性


### 四、 2019/11/17
* 1 . 修改 `SafeKeyboard` 显示后遮住目标 `EditText` 问题 (被遮挡时顶起目标 `EditText` 父 `View`) 功能实现逻辑, 解决动画效果不尽如人意的 `BUG`.
* 2 . 增加按键震动功能(可选)


### 三、 2019/09/26
* 1 . 解决 `SafeKeyboard` 在 `PopupWindow` 中显示会崩溃的问题 (关闭按键预览功能即可). 见 `issue#3`
* 2 . 解决 `SafeKeyboard` 显示后遮住目标 `EditText` 问题 (被遮挡时顶起目标 `EditText` 父 `View`). 见 `issue#8`
  <br>暂时只提供这一种解决方案 ( 尚有改进空间 )
* 3 . 适配 `ScrollView` 中的 `EditText` 使用 `SafeKeyboard` 功能. 详见: &nbsp;&nbsp;[注意事项 (SafeKeyboard_Note)](https://github.com/SValence/SafeKeyboard/wiki/Attention-Note)
* 4 . 解决 `SafeKeyboard` 在 `AlertDialog` 中显示无法点击的问题. 采用 `DialogFragment` 来实现该功能.
* 5 . 修改多个 `EditText` 共用一个 `SafeKeyboard` 时, `OnTouch` 事件造成 `SafeKeyboard` 显示混乱的 BUG.
* 6 . 简化部分 API 调用代码, 并增加一个有数字的字母键盘.


### 二、 2019/06/22
* 1 . 支持多个 `EditText` 共用一个 `SafeKeyboard`, 各键盘无缝切换
* 2 . 支持根据不同 `EditText` 的 `InputType` 默认使用不同的键盘(目前仅支持数字键盘和身份证键盘)
* 3 . 支持锁定英文大写
* 4 . 增加两种数字键盘、增加一个身份证键盘, 对两种键盘的数字支持随机显示
* 5 . `SafeKeyboard` 提供接口指定显示身份证键盘的 `EditText`
* 6 . 支持记住每个 `EditText` 对应的上次打开的键盘类型, 再次显示 `SafeKeyboard` 时显示该中类型键盘, 此功能可在 `SafeKeyboardView` 的属性中 打开/关闭
* 7 . 项目本身支持 lambda 表达式

### 一、 2018/07/29
* 1 . `AndroidManifest.xml` 文件中添加 `"android:windowSoftInputMode="stateAlwaysHidden">"`, 兼容低版本系统, 重新进入软件界面系统软键盘自动弹出的问题。
* 2 . 解决特殊键盘图标在不同屏幕上显示变形问题, 不需要手动设置图片显示时与按键边界的边距。
* 3 . `SafeKeyboard` 提供接口设置特殊按键的自定义图片
