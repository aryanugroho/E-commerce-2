# ����ĵ�
  ��git��Downloads

# ����
* �������ݿ���ϱ���utf8,�Է�ֹ�������ݵ�����
```
create database shopxx DEFAULT CHARSET utf8 COLLATE utf8_general_ci;
```

* ����eclipse����Ҫ����jre,���̱���Ϊutf8

* ��װ��ɺ�Ҫ����tomcat

* ������Ϊ���룬 server.xml�е�Connector�ڵ�����URIEncoding="UTF-8",�ο�����
```
 <Connector port="80" protocol="HTTP/1.1" 
               connectionTimeout="20000" 
               redirectPort="8443" URIEncoding="UTF-8" compression="on" compressableMimeType="text/html,text/css,text/javascript" />


```

* ���޸�java���ǰ̨չʾû����Ч��Ϊ�����ԭ���ڹ���ϵͳ�У�����-->��̬������--> ��ҳ/��Ʒ/���� --> ȷ������ջ��棬ҳ�漴����Ч,Ĭ�ϻ���λ��ΪSystem.getProperty("java.io.tmpdir")

* ���°�װɾ��/install/install_lock.conf�ļ�,��Ϊeclipse,ȥĿ¼$WORKSPACE_PATH$\.metadata\.plugins\org.eclipse.wst.server.core\tmp0\wtpwebapps\�鿴

# git����
```
# init
mkdir /path/to/your/project
cd /path/to/your/project
git init
git remote add origin https://xghrbc1001@bitbucket.org/xcjTeadm/guilin.git

# clone
eg: git clone https://xghrbc1001@bitbucket.org/xcjTeadm/guilin.git(�轫xghrbc1001�����Լ����û���)


# push to remote
git push origin master

# ���ȴ�Զ�̵�origin��master����֧�������µİ汾��origin/master��֧��,Ȼ��Ƚϱ��ص�master��֧��origin/master��֧�Ĳ��,�����кϲ�
git fetch origin master
git log -p master..origin/master
git merge origin/master

# ��Զ�̻�ȡ���µİ汾�����ص�tmp��֧��,֮���ٽ��бȽϺϲ�
git fetch origin master:tmp
git diff tmp 
git merge tmp

# reset
staging --> untrack

# git add/rm
unstrack--> staging

# git commit
staaging --> staged

# git push
staged --> server

# git pull
server  --> staged

# git tag
git tag -a 0.0.1 -m 'Realease version'
git push --tags
git tag -d 0.0.1
git push :refs/tags/0.0.1

# git checkout [path/.]
remove from unstrack,staging,staged

# git diff tool
git config --global diff.tool meld
git config --global merge.tool meld

```

# ���칤�����
* �ܶ�����д����·����eg :CaptchaEngine.java,�滻/net/shopxx/

# ����
## �ͻ�����
* ��һ������trip.taobao.com
* ������
* ֧�ֶ๩Ӧ�� 
* ���Ա�����ַ http://gllygf.tmall.com

## www.youguilin.com.cn ��̨�ʺ�
* ��ַ�� http://supplier.youguilin.com.cn/login.aspx?tip=nologin&time=1398358085329
* ������:�û���:LXS����    ����:123456
* ����:�û���:JQ�콭       ����:123456
* �Ƶ�:�û���:JD��ɤ��     ����:123456

## �ɲο���һЩ��ַ
* www.nuomi.com �������̿ɲο���ʵ��������Ʒ����
* www.zuitu.com ��Ӧ�̹����ɲο����

## ��ʾ������
* http://124.227.108.106:8181/youguilin/
* rdesktop -u administrator -p password  124.227.108.106:1918

# Schedule

## һ�ڣ�����Ʊ���������������ʾ���ͻ���)
### ����
* ��Ʊ���Ƶ����µ�ʱ������Ҫ��ַ,���ͷ�ʽ(Ҳ���԰Ѷ��ţ����֤�������ͷ�ʽ)
* �û����ģ���Ϊ��Ʊ���û��������·��Ͷ���
* �û����ģ��������飬����ʾ��ά������ִ�
* ���������״̬����ʹ��
* ����ϵͳ������������Ϊ������Ʒ����������,������Ϊ���Ͷ���
* �ο�ʵ�ַ�ʽ����ͨ����Ʒ���������а󶨡�shopxx�����ͷ�ʽ����֧����ʽ�󶨵�
* �������Ʊ,��Ʊ����չ����Ʊֻ�����к��ŵĽӿ�

### ��Ӧ��
### Ӳ��

# ��Ŀ���
* ���Ͷ��� SmsService.java
* �ʼ� youguiling123@163.com  youguiling smtp.163.com  25

# ������ء�
## eclipse����maven��web��Ŀȴ��ʾ����web��Ŀ��ô��
* mvn eclipse:eclipse -Dwtpversion=1.0

## SampleController
```
/**
* http://localhost:8080/guilin/hello/view.jhtml?username=test
**/
```
��SampleController
template/shop���½�hello/world/view.ftl
	
## img lazyload
* http://www.appelsiini.net/projects/lazyload

## �ֲ�
* http://www.bootcss.com/p/unslider/
* ���λ����,���λ��С: 965*270
```
<ul>
	[#list adPosition.ads as ad]
		[#if ad.hasBegun() && !ad.hasEnded() && ad.type == "image"]
			[#if ad.url??]
				<li><a href="${ad.url}">
					<img src="${ad.path}" width="${adPosition.width}" height="${adPosition.height}" alt="${ad.title}" title="${ad.title}" />
				</a></li>
			[#else]
				<li><img src="${ad.path}" width="${adPosition.width}" height="${adPosition.height}" alt="${ad.title}" title="${ad.title}" /></li>
			[/#if]
		[/#if]
	[/#list]
</ul>
```

## ֧�����
```
1���ο�������net.shopxx.plugin.alipayDirect��
2�������������ơ������(AlipayDirectPlugin.java)���ơ����ÿ�������(AlipayDirectController.java)���ơ�������ͼ(setting.ftl)����
3���޸Ĳ�����@Componentע��ֵ����֤��Ωһ
4���޸Ĳ����ʵ�ַ������������£�
/**
* ��ȡ�������
*/
public abstract String getName();

/**
* ��ȡ����汾
*/
public abstract String getVersion();

/**
* ��ȡ�������
*/
public abstract String getAuthor();

/**
* ��ȡ�����ַ
*/
public abstract String getSiteUrl();

/**
* ��ȡ��װURL�������̨�����װ���ӵ�ַ��������Ҫ��װ���ܷ���null������Ҫ�ù��ܣ����д��Ӧ���ÿ�������
*/
public abstract String getInstallUrl();

/**
* ��ȡж��URL�������̨���ж�����ӵ�ַ��������Ҫж�ع��ܷ���null������Ҫ�ù��ܣ����д��Ӧ���ÿ�������
*/
public abstract String getUninstallUrl();

/**
* ��ȡ����URL�������̨����������ӵ�ַ��������Ҫ���ù��ܷ���null������Ҫ�ù��ܣ����д��Ӧ���ÿ�������
*/
public abstract String getSettingUrl();

/**
* ��ȡ����URL����ת��������֧�������URL
*/
public abstract String getRequestUrl();

/**
* ��ȡ���󷽷�����ת��������֧����������󷽷�
*/
public abstract RequestMethod getRequestMethod();

/**
* ��ȡ�����ַ����룬��ת��������֧��������ַ�����
*/
public abstract String getRequestCharset();

/**
* ��ȡ�����������ת��������֧��������������
* 
* @param sn
*            ���
* @param description
*            ����
* @param request
*            httpServletRequest
* @return �������
*/
public abstract Map<String, Object> getParameterMap(String sn, String description, HttpServletRequest request);

/**
* ��֤֪ͨ�Ƿ�Ϸ�����֤������֧����ɺ�ķ��ؽ���Ƿ�Ϸ�
* 
* @param sn
*            ���
* @param notifyMethod
*            ֪ͨ����
* @param request
*            httpServletRequest
* @return ֪ͨ�Ƿ�Ϸ�
*/
public abstract boolean verifyNotify(String sn, NotifyMethod notifyMethod, HttpServletRequest request);

/**
* ��ȡ֪ͨ������Ϣ���յ�������֧����ɺ�ķ��ؽ������Ӧ
* 
* @param sn
*            ���
* @param notifyMethod
*            ֪ͨ����
* @param request
*            httpServletRequest
* @return ֪ͨ������Ϣ
*/
public abstract String getNotifyMessage(String sn, NotifyMethod notifyMethod, HttpServletRequest request);

/**
* ��ȡ��ʱʱ�䣬֧����ʱʱ��
*/
public abstract Integer getTimeout();
```

# csdn
* 353454657  20401903 qq

# ���й�����ʾdemo
* git���ļ�demo.rar,��201405�ļ��зŵ�upload/Ŀ¼
* ��װ����
* ��װ���,����mysql(�����뱨�����ڴ���,drop�����ݿ�)
```
source /home/beni/guilin/guilin/WebContent/install/data/mysql/guilin.sql

```

# �ƶ��˼���
* ionic
* appcan

# ����
* ������Ʒ
* �������մ� ciduci.cn dataoci.com china-ciqi.com
* ��ũ�̳�
* Ȥ����
* ������������

# stock
* ���̻� honglvhui.com
* zhang-die
* ztjtmt.com
* hongyulv.com
