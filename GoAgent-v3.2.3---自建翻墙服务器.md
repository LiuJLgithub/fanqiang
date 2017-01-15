
<p  ><b>前言</b></p>

<ul >
 <li >本教程是为我分享的软件<u><a
     href="https://github.com/bannedbook/fanqiang/wiki/Chrome%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">Chrome一键翻墙包</a></u>和<u><a
     href="https://github.com/bannedbook/fanqiang/wiki/%E7%81%AB%E7%8B%90firefox%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">火狐firefox一键翻墙包</a></u>而写的，因为google的不断升级，网上很多自建流量的教程已失效，所以特意撰写此教程。因为<u><a
     href="https://github.com/bannedbook/fanqiang/wiki/Chrome%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">Chrome一键翻墙包</a></u>和<u><a
     href="https://github.com/bannedbook/fanqiang/wiki/%E7%81%AB%E7%8B%90firefox%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">火狐firefox一键翻墙包</a></u>是多人共用流量，所以随着使用人数的增加，可能有一天无法满足更多使用者的流量需求。为此，特把自建流量的详细方法写出来，让对电脑有一定基础的使用者可以创建自己的流量，从而不受流量不够带来的影响。没有电脑基础的朋友，如果你有耐心，严格按照教程的步骤操作，也是可以成功的。</li>
 <li >使用自建的流量还可以解决访问一些网站出现Hosts Deny的问题。也可以解决appid失效而出现的“Error: Not Found-The
     requested URL /_gh/ was not found on this server.” 的问题。</li>

 <li >本页面短网址：https://git.io/zjfq</li>
</ul>

<p>&nbsp;</p>

<p  ><b>一、申请 Google App Engine
并创建 appid</b></p>

<ol start=1 type=1>
 <li >申请注册一个 <a
     href="https://appengine.google.com" target="_blank">Google App Engine</a> 账号。没有 Gmail 账号先注册一个， 用你的 Gmail 账号登录。 申请 GAE 帐号： </li>
 <li >登录之后，访问<a
     href="https://appengine.google.com" target="_blank">Google App Engine</a>&nbsp;
     <a href="https://appengine.google.com/">https://appengine.google.com/</a>&nbsp;&nbsp;
     自动转向创建项目页面，如下图：<br>
     <img border=0 width=416 height=178 src="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/GoAgent.files/image001.jpg"><br>
     点“创建项目”按钮，出现下图：</li>
</ol>

<p  ><img border=0 width=487
height=388 src="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/GoAgent.files/image002.jpg"></p>

<p  >填写好项目名称，然后会自动出现：您的项目 ID 将为 jinwen0001，
注意：项目名称和项目ID可能是不一样的，这个自动出现的项目ID就是我们后面要用到的appid ，要记录下来备用。<br>
点“显示高级选项”，选择APP引擎的位置为：us-east1
(选美国西部，可能速度快些)<br>
然后，2个单选按钮都选 是，然后点“创建”按钮。</p>

<p  >&nbsp;</p>

<ol start=3 type=1>
 <li >稍等片刻，创建项目成功后出现如下页面：</li>
</ol>

<p  ><img
border=0 width=327 height=201 src="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/GoAgent.files/image003.jpg"></p>

<p  >这样一个GAE应用被激活，该应用对应的appid 就是项目 ID：jinwen0001，注意不是项目名称，项目名称和ID可能不一样。</p>

<ol start=4 type=1>
 <li >创建更多项目：<br>
     如下图点页面左上方的项目名称，然后点创建项目，重复上面的步骤，就可以创建多个GAE应用。<br>
     <img border=0 width=452 height=197 src="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/GoAgent.files/image004.jpg"></li>
</ol>

<p  >一个Gmail账户可以创建多个GAE应用，每个应用每天 1G 免费流量，当天的流量用完后会在<a
href="http://zh.thetimenow.com/united_states/california/san_francisco">美国加州时间零时</a>重置。这里我们示范，只创建一个应用就可以了。</p>

<p  ><b>二、下载 goagent 并上传至 Google App Engine</b></p>

<ol start=1 type=1>
 <li >打开我发的<u><a
     href="https://github.com/bannedbook/fanqiang/wiki/Chrome%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">Chrome一键翻墙包</a></u>，并确保能正常打开墙外网站，然后不要关闭代理软件那个黑色窗口。</li>
 <li >将IE代理服务器设置成127.0.0.1:8087</li>
 <li >下载 goagent 并解压（如果已随本教程一起获得goagent服务端程序，则可不必下载，服务端程序仅包括3个文件：app.yaml、gae.py和legacy.py）： <a
     href="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/goagent.zip">https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/goagent.zip</a>
     </li>
 <li >解压后，用记事本打开app.yaml，把里面的第一行的YourAppid&nbsp; 替换为你自己申请到的appid，这里我们替换为：jinwen0001</li>
 <li >下载python2.xx,注意不要下载3.xx &nbsp;<a
     href="https://www.python.org/downloads/">https://www.python.org/downloads/</a>
     （不翻墙可下载）并安装之。</li>
 <li >下载Google_App_Engine_SDK_for_Python （需翻墙下载）<a
     href="https://cloud.google.com/appengine/downloads#Google_App_Engine_SDK_for_Python">https://cloud.google.com/appengine/downloads#Google_App_Engine_SDK_for_Python</a>
     &nbsp;并安装之。</li>
 <li >安装Google_App_Engine_SDK_for_Python后桌面上出现一个Google App Engine Launcher的图标，双击启动之。</li>
 <li >然后点菜单：File/Add Existing Application…,如下图</li>
</ol>

<p  ><img border=0 width=238
height=148 src="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/GoAgent.files/image005.jpg"></p>

<p  >然后，点“Browse…”按钮找到app.yaml所在路径，如下图：</p>

<p  ><img border=0 width=522
height=215 src="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/GoAgent.files/image006.jpg"></p>

<p  >然后点“Add”按钮，出现如下画面：</p>

<p  ><img border=0 width=483
height=139 src="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/GoAgent.files/image007.jpg"></p>

<p  >选中jinwen0001 这一行，然后右上角的点击“Deploy”按钮，然后会自动打开浏览器，出现如下画面（如果你的翻墙浏览器不是默认浏览器，那么把自动打开的网址，复制到已翻墙并登录google的浏览器中）</p>

<p  ><img border=0 width=483
height=506 src="https://raw.githubusercontent.com/bannedbook/fanqiang/master/gae/GoAgent.files/image008.jpg"></p>

<p  >然后，点击上图的“允许”按钮，接下来，就出现一些信息如下：</p>

<p  >&nbsp;</p>

<p  >Authentication successful.</p>

<p  >... </p>

<p  >... </p>

<p  >06:22 PM Deployment successful.</p>

<p  >06:22 PM Checking if updated app version is
serving.</p>

<p  >06:22 PM Completed update of app: jinwen0001, version:
1</p>

<p  >2016-08-08 18:22:22 (Process exited with code 0)</p>

<p  >You can close this window now.</p>

<p  >这样就上传成功了。可以用已翻墙的浏览器试试访问：<a href="http://jinwen0001.appspot.com/">http://jinwen0001.appspot.com/</a></p>

<p  >可以看到提示信息：</p>

<blockquote>GoAgent 服务端已经在 2016-08-08 16:22:12 升级到 3.2.0 版本, 请更新您的客户端。</blockquote>
<p  >说明GoAgent 服务端已部署成功啦。</p>

<p  >这时也可以打开GAE首页：<a href="https://appengine.google.com/">https://appengine.google.com/</a>
，看看创建的appid的状态。 </p>

<ol start=9 type=1>
 <li >将前面设置的IE代理取消。</li>
</ol>

<p  >&nbsp;</p>

<p  ><b>三、将上传成功的appid添加到GoAgent的配置文件中：</b></p>

<p  ><b>1.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </b>如果你正在用我分享的<a
href="https://github.com/bannedbook/fanqiang/wiki/Chrome%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">ChromeGo</a>和<a
href="https://github.com/bannedbook/fanqiang/wiki/%E7%81%AB%E7%8B%90firefox%E4%B8%80%E9%94%AE%E7%BF%BB%E5%A2%99%E5%8C%85">FirefoxFQ</a>两个软件，里面有一个<b>Agent</b>文件夹，Agent文件夹内有个<b>proxy.ini</b>文件，这个就是配置文件（<b>注：</b>如果你的系统隐藏了已知文件类型的扩展名，那你需要在文件夹选项里取消这一项，不然可能会看不到.ini扩展名），用记事本打开它<b>（最好是用文本编辑器</b><b>EmEditor</b><b>或者</b><b>notepad++</b><b>打开，用记事本有时会出现乱码）</b>，把文件中的[gae]小节的appid
=后面的值替换为你自己的appid，我们这里替换为jinwen0001，如果有多个appid，用 | 隔开，替换后是这样的：<br>
[gae]<br>
enable = 1<br>
appid = jinwen0001| jinwen0002| jinwen0003<br>
path = /_gh/<br>
mode = https<br>
ipv6 = 0<br>
......</p>

<p  ><b>2.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </b>上一步确认无误后，点记事本或文本编辑器左上方菜单栏的“<b>文件</b>”，弹出菜单中点“<b>保存</b>”，然后关闭这个proxy.ini的文件窗口。</p>

<p  ><b>四、重新启动软件测试appid是否可以正常使用。</b></p>

<p  ><b>1.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </b>打开一个墙外网站看看，能打开一般来说就没问题。</p>

<p  ><b>2.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </b>那么怎样查看是不是使用自己创建的appid在翻墙呢？方法很多，当然如果你严格按照上面的步骤操作，那用的一定是你自己的appid。</p>

<p  ><b>3.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </b>使用一段时间后，可以去<a
href="https://appengine.google.com/">GAE首页</a>，点击每个appid的名字就可以查看流量使用情况。</p>

<p  ><b>五、反馈交流</b></p>

<p  style='margin-top:13.4pt;margin-right:0cm;
margin-bottom:13.4pt;margin-left:18.0pt;text-align:left;line-height:20.1pt;
background:white'>自建流量的过程到这里基本也就结束了，如果哪一步还有疑问，<a href="https://github.com/bannedbook/fanqiang/issues">请发帖反馈交流</a></p>
