# TextView详解和常用属性

## TextView简介

向用户显示文本，并允许用户编辑文本。TextView是一个完整的文本编辑器，但基类被配置为不允许编辑。

其在xml里面的基本使用：

```xml
 <LinearLayout
      xmlns:android="http://schemas.android.com/apk/res/android"
      android:layout_width="match_parent"
      android:layout_height="match_parent">
    <TextView
        android:id="@+id/text_view_id"
        android:layout_height="wrap_content"
        android:layout_width="wrap_content"
        android:text="@string/hello" />
 </LinearLayout>
```

在Android开发中，TextView是比较常用的控件，展示文本信息，其属性也是比较繁多的，可设置文字的字体大小、颜色、背景色、边距等基本样式。

## 继承关系

TextView作为顶层View，可以算作一个大类，其继承了View，是Button、EditText等多个关键控件类的父类。

- Button：用户可以点击或单击以执行操作的用户界面元素。
- CheckedTextView：TextView支持Checkable界面和显示的扩展。
- Chronometer：实现简单计时器的类。
- DigitalClock：已弃用，可用TextClock替代。
- mEditText：用于输入和修改文本的用户界面元素。
- TextClock：可以将当前日期或时间显示为格式化字符串，可以利用它显示实时刷新的当前时间。

## 常用属性

```java

//部分布局属性（继承View）
layout_width：控件宽度。
layout_height：控件高度。
android:gravity：内部对齐方式：左对齐，右对齐，居中对齐，顶部对齐，底部对齐。
android:layout_gravity：外部对齐方式：左对齐，右对齐，居中对齐，顶部对齐，底部对齐。

//控制输入文本（EditView时弹出的软键盘也会不同）
android:inputType：设置文本的数据类型，如果包含非该类型的文本则不显示，如设置为number类型，如果文本有非数字类型文本，则文本显示不出来。
	类型：
		"none"：输入普通字符
		"text"：输入普通字符
		"textCapCharacters"：输入普通字符
		"textCapWords"：单词首字母大小
		"textCapSentences"：仅第一个字母大小
		"textAutoCorrect"：前两个自动完成
		"textAutoComplete"：前两个自动完成
		"textMultiLine"：多行输入
		"textImeMultiLine"：输入法多行（不一定支持）
		"textNoSuggestions"：不提示
		"textUri"：URI格式
		"textEmailAddress"：电子邮件地址格式
		"textEmailSubject"：邮件主题格式
		"textShortMessage"：短消息格式
		"textLongMessage"：长消息格式
		"textPersonName"：人名格式
		"textPostalAddress"：邮政格式
		"textPassword"：密码格式
		"textVisiblePassword"：密码可见格式
		"textWebEditText"：作为网页表单的文本格式
		"textFilter"：文本筛选格式
		"textPhonetic"：拼音输入格式
		"number"：数字格式（不能输入小数点）
		"numberSigned"：有符号数字格式
		"numberDecimal"：可以带小数点的浮点格式（可输入小数点）
		"phone"：拨号键盘
		"datetime"：日期+时间格式
		"date"：日期键盘
		"time"：时间键盘
	
//图片和文字共用		
android:drawableBottom：TextVie底部出现一张图片，设置图片地址。
android:drawableEnd：TextView右侧出现一张图片。
android:drawableRight：TextView右侧出现一张图片。
android:drawableLeft：TextView左侧出现一张图片。
android:drawableStart：TextView左侧出现一张图片。
android:drawableTop：TextView上部出现一张图片。
android:drawablePadding：设置text与drawable（图片等）的间隔，一般都与drawableLeft、drawableStart 、drawableEnd 、drawableRight、drawableTop、drawableBottom一起使用。

//控制文本显示（EditView时控制输入）
android:lines：设置文本多少行，当长度超出该值时，超出文本部分不显示，和android:minLines属性类似。
android:maxLines：设置文本最大多少行，当文本达到改行数还没显示完，超出部分不显示，和android:lines属性类似。
android:maxLength：控制文本最多显示/输入多少个字符。
android:minLines：限制文本最低多少行显示。
android:singleLine：布尔类型，表示是否单行显示，已经废弃，建议用android:lines。
android:ellipsize：设置省略号（"start"：省略号显示在开头、"end"：省略号显示在结尾、"middle"：省略号显示在中间、"marquee" ：以 “跑马灯” 的方式显示，动画横向移动），如果 TextView 的 layout_width 和 layout_height 是指定了像素的固定宽高，该属性会直接生效，如果宽高是"wrap_content"类型的，则需要同时结合"android:maxLines"和"android:maxEms"属性才可生效。
android:ems：代表的是字符M的宽度，注意不同的设备M的宽度不同，假设设置为6，则可显示文本的长度为6个M的长度。
android:maxEms：设置显示最多ems宽。
android:minEms：设置显示最小ems宽。

//文本样式
android:lineSpacingExtra：文本行间距
android:text：设置显示的文本。
android:textSize：设置文本大小。
android:textColor：设置文本的颜色。
android:textStyle：设置文本样式，文字斜体、加粗("normal|italic|bold")，或者通过xml文件同时设置多个textView的属性，复用样式。
android:typeface：设置文本的字体，monospace：等宽字体，sans：无衬线字体，serif：衬线，normal：普通字体。
android:fontFamily：字体组合，里面有多个字体，可搭配字体权重，引用的是xml文件，例如 android:fontFamily="@font/myfont"，文件新建在"res->font"中。
android:textFontWeight：设置使用的字体的权重，权重高使用谁，和android:fontFamily一起使用。
android:hint：文本在文本空时提示文本。
android:textColorHint：设置android:hint属性文本的颜色。
android:shadowColor：设置所有文本阴影的颜色，shadowColor、shadowDx、shadowDy、shadowRadius同时使用实现立体文字效果。
android:shadowDx：设置所有文本 x 轴即水平偏移，右为正，左为负，shadowColor、shadowDx、shadowDy、shadowRadius同时使用实现立体文字效果。
android:shadowDy：设置所有文本y轴即垂直偏移，下为正，上为负，shadowColor、shadowDx、shadowDy、shadowRadius同时使用实现立体文字效果。
android:shadowRadius：设置所有文本阴影的半径，shadowColor、shadowDx、shadowDy、shadowRadius同时使用实现立体文字效果，味道极佳。
android:textScaleX：设置文本的水平缩放程度，大于1，x方向拉长加粗，小于1，x方向缩短变细。
android:textColorHighlight：设置点击后文本的背景色，比如 android:autoLink="web" 为超链接的时候，点击后背景色会展示 android:textColorHighlight 设置的颜色。
android:textColorLink：设置文本是链接类型的颜色，和android:autoLink="web"联合使用。

//其他
android:textCursorDrawable：设置光标颜色，应用在EditText输入框View中，自定义的drawable文件。
android:autoLink：指定连接形式文字，可以是（"web"：匹配网页模式，点击跳转浏览器应用打开网页、"all"：匹配所有模式（相当于网络/电子邮件/电话/图）、"email"：匹配电子邮件地址，点击后自动跳转邮箱相关的应用、"phone"：匹配电子邮件地，点击后自动跳转拨号页面、"none"：默认值，什么也没有）。
android:enabled：设置控件针对点击事件是否启用，每个view都有，设置为true则点击事件无响应。


```

## 高级玩法

- 设置背景颜色和背景图片
- 