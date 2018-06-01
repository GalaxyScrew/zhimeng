# zhimeng
织梦关于xss引起的小bug  

织梦的xss过滤代码：/include/helpers/filter.helper.php RemoveXSS  
织梦的xss过滤时是会过滤html标签和事件的，其中它过滤掉了base标签,  
而它的会员基本资料的访问url为edit_baseinfo.php,  
在需要过滤时，在baseinfo之间加入了<x>，即变成base<x>info导致无法访问;  
具体出错的场景是在基本资料设置页面退出重登后通过gourl访问失败.  
解决方法：修改edit_baseinfo.php文件名，同时相关引用也要注意修改
