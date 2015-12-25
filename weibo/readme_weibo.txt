1、需求分析
		电脑网站   pad http://weibo.com/u/1823706963
		手机网站  兼容性(opera,moz,webkit) http://m.weibo.cn/u/1823706963

2、界面设计

3、框架搭建
   列式布局

4.页面制作
5.购买域名上线
6.迭代更新


代码编写：
phone
1、头部背景图片的样式
2、默认1em=16px,在font-size里可以设置1em=多少
3、头部个人信息的排版
   position:absolute，开始设置的left:15px，导致浏览器下发有滚动条
   去掉滚动条的方法：给个人信息的父div里包含头像的div设置padding:15px
4、保证标签按等比拉伸display:flex
	.menu{ width: 100%;display: flex;display:-webkit-flex;}
	.menu a{ display: block;font-size: 12px;}
5、最好不要在菜单的a标签里放置背景，因为a标签的背景会随浏览器的分辨率变化而变大或变小，在a标签放置div或者span


pad
1、title背景的位置
2、不改变原来布局的前提下，修改个人信息位置的样式
3、整个页面的背景
   设置整个背景颜色，并将顶部图片固定
4、个性签名和菜单加关注和私信在不修改界面位置的情况下，通过 position:absolute定位来控制菜单关注和私信的位置
.item-list .item2{position: absolute;margin: 40px auto 10px -60px;width: 350px;}
5、导航菜单
   保持下方边框比字体的宽度稍长，设置padding:0 10px 0 10px
6、设置打开页面时的动画
   animation: weibo_bg_ani 3s linear;
   @keyframes weibo_bg_ani{ 
			from{transform:scale(1.1,1.1)}
			to{transform:scale(1.05,1.05)}
		}

7、一般情况下，网页运行时，不管标签是不是display：none，都会加载图片和内容；
但是在响应式布局情况下：会优先加载当前设备显示的所需的css样式


综合时，
   将公用代码放置common.css；并将适用于不同分配率的样式，分别放置到不同的css文件中，将每个文件中某些公有的属性(text-align,display等)，挑出来公共设置。

