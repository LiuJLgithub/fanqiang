
<h2>前言</h2>

<ul type=disc>
 <li >本教程是为我分享的软件<a
     href="https://github.com/bannedbook/fanqiang/wiki/Chrome%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">Chrome一键翻墙包</a>和<a
     href="https://github.com/bannedbook/fanqiang/wiki/%E7%81%AB%E7%8B%90firefox%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">火狐firefox一键翻墙包</a>而写的，虽然这2个翻墙包都已携带三种翻墙软件，其中的GoAgent也会每日自动更新IP，大多数网友都可以利用来成功翻墙。但大陆网络环境错综复杂，个别网友反馈GoAgent翻墙不太稳定甚至无法翻墙，因此向大家介绍GoAgent扫描和更新IP的方法。让对电脑有一定基础的使用者可以自己扫描和更新IP，从而在自己的网络环境更加快速的翻墙，没有电脑基础的朋友，如果你有耐心，严格按照教程的步骤操作，也是可以成功的。</li>
 <li >如果使用中出现：<b>Over Quota</b><b>、</b><b>Hosts DenyURL </b><b>或</b><b> /_gh/ was not found </b><b>或者</b><b> </b><b>只能访问谷歌不能访问其它网站</b><b> </b>的问题，请依照“<a
     href="https://github.com/bannedbook/fanqiang/wiki/GoAgent-v3.2.3---%E8%87%AA%E5%BB%BA%E7%BF%BB%E5%A2%99%E6%9C%8D%E5%8A%A1%E5%99%A8">GoAgent自建流量教程</a>”来创建自己的appid，建议有一点电脑基础的朋友自建流量。</li>

 <li >本页面短网址：https://git.io/scanip</li>
</ul>

<p >&nbsp;</p>

<h2>一、下载和替换proxy.py文件</h2>

<p   >下载(右键点击，另存为即可下载) <a
href="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/proxy.py">proxy.py文件</a>，用其覆盖替换Agent文件夹里的同名文件。替换proxy.py文件后，GoAgent将不会自动更新ip了，从此你需要自己定期扫描和更新ip。</p>

<h2>二、GoAgent扫描IP</h2>

<p >你可以直接用Agent文件夹下的gsan目录里的工具即可扫描了，已经内置了可用ip列表大约1.6w ip。</p>

<p >若你有自己有扫描工具，可以下载<a
href="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/googleip.txt">
googleip.txt文件</a>，其为为可用谷歌ip的地址列表，大约2w个ip，来源为vpn扫描全部谷歌地址域得到，可靠性有保障，大家可以下载来自己用<a
href="https://code.google.com/archive/p/gogo-tester/">GoGoTest</a>、GScan进行扫描！</p>


<h2>三、将扫描到的可用IP添加到GoAgent的配置文件中</h2>

<p   ><b>1.&nbsp; </b>如果你正在用我分享的<a
href="https://github.com/bannedbook/fanqiang/wiki/Chrome%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">ChromeGo</a>和<a
href="https://github.com/bannedbook/fanqiang/wiki/%E7%81%AB%E7%8B%90firefox%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">FirefoxFQ</a>两个软件，里面有一个<b>Agent</b>文件夹，Agent文件夹内有个<b>proxy.ini</b>文件，这个就是配置文件（<b>注：</b>如果你的系统隐藏了已知文件类型的扩展名，那你需要在文件夹选项里取消这一项，不然可能会看不到.ini扩展名），注意，请不要修改<b>proxy.ini</b>文件。把<b>proxy.ini</b>文件拷贝粘贴成另一个文件，把拷贝的新文件改名为：proxy.user.ini
，然后编辑这个proxy.user.ini文件<b>（最好是用文本编辑器</b><b>EmEditor</b><b>或者</b><b>notepad++</b><b>打开，用记事本有时会出现乱码）</b>，把文件中的[iplist]小节的google_cn
= 、google_hk
= 后面的值替换为你扫描到的可用ip，多个ip用|隔开，比如：202.86.162.148|59.18.46.11|59.18.46.19|59.18.45.41<br>
替换后大概是这个样子：<br>
google_cn = 202.86.162.148|59.18.46.11|59.18.46.19|59.18.45.41|59.18.45.35<br>
google_hk = 202.86.162.148|59.18.46.11|59.18.46.19|59.18.45.41|59.18.45.35</p>

<p   ><b>2.&nbsp;</b>google_cn和google_hk的ip是否需要换成一样的ip？&nbsp;<br>
&nbsp;这个随你便，只要ip未被干扰，是否一样没要求。&nbsp;</p>

<p   ><b>3.&nbsp; </b>上一步确认无误后，点记事本或文本编辑器左上方菜单栏的“<b>文件</b>”，弹出菜单中点“<b>保存</b>”，然后关闭这个proxy.user.ini
的文件窗口。</p>

<p ><b>四、重新启动软件测试是否可以正常使用</b></p>

<p   >打开一个墙外网站看看，能打开一般来说就没问题。</p>

<p ><b>五、反馈交流</b></p>

<p>GoAgent扫描和更新IP的过程到这里基本也就结束了，如果哪一步还有疑问，请点下面的翻墙交流链接发帖交流。</p>