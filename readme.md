# 塔斯汀小程序模仿项目


- 本项目归塔斯汀所有， 只做学习所用， 请尊重原厂版权

- fiddler  抓包工具抓取图片

- 界面模仿采用 markman 做标记
 1. 我们没有设计稿， 如何 1:1 还原小程序？
 2. 拍屏得到小程序截图
 3. 使用在线大小[转换工具](https://www.gaitubao.com/)， 将图片改成750
  以后在写项目的时候，直接量像素就可以写进去，因为小程序以750rpx作为设计稿标准大小
  帮我们自动适配，很好用
4. 使用[markman](http://www.getmarkman.com/),先标注，再写样式
  以后呢，上了班就不用了， 有设计师给你标好
  现在， 还是自己来LOL 吧

- 项目配置在根目录 app.json
  - 隐藏并定制 navigationBar
    "navigationStyle": "custom"
  - 启动定位功能

- 使用了 BEM 国际css命名规范
  tst_banners 广告位 Block
  tst_banners__img  Element

- css 技巧
  1. 能不用定位就不要用定位
    脱离文档流
  2. 移动端多用弹性布局

- 弹性布局
  移动端 flex 可以解决大部分问题
  div 块级
  布局的一种  跟外部不一样的布局， 桃花源记
  flex 内部  块级能力丢失   BFC
  Block formating context

- BEM 国际命名规范
  Block 开始 rx_tab 新的组件
  Element 内部元素的声明  rx_tab__item
  Modifier  rx_tab__item-on


- git 提交
  1. 第一次 git 命令行提交
    全局配置 git config --global user.name "Songlin Ye"
      git config --global user.email "1379728314@qq.com"



- 滴滴swiper 多页活动菜单功能
  1. 用户体验 less is more  摆在第一位
    菜单太多， 用户的密集恐惧症， 把重要的放在首页
    其他的可以多放一些

- css 的技巧
  1. 选择器优先级
    p.md2 11
    p.md2 + div.md3    22
    标签 1 < 类名 10 < id 100 < 计算表达式
  2. 行内样式， 优先级更高  少用
  3. !important 优先级最高  慎用
    {{}} 占位符   返回值是替换的值
  4. swiper bindchange 事件
    event 对象中
      event.detail.current 当前是第几个 swiper-item?
      menu_type
      this.setData()
      
- 数据响应式编程
  它是一个思想， 有别于DOM 编程API
  设置一些页面效果，操作的不是DOM
  操作的是数据，因为数据一旦发生改变，页面会自动刷新
  1. 滴滴可变高度的首页菜单
  2. tabbar 组件
    data  添加  tab 属性，  表示当前哪个 tab 被激活
    tab-item 添加 bindtap 事件
    tab-item data-tab   数据属性  data-xxxx
    e.currentTarget 点击当前元素
    e.currentTarget.dataset.tab 数据
  3. 外卖品类及菜单数据设计
    2个 scroll-view, 数据是有相关性的
    2层嵌套的 json 结构
    [ 分类数组
      {
        菜品数组： [
          
        ]
      }
    ]
