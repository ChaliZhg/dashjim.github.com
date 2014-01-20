---
layout: post
title: ����TCP���������磨3G����ʵʱӦ����Ҫע�������
categories:
- Telecom
tags:
- Flex, Adobe AIR, Video, TCP
---

     
	 
����TCP���������磨3G�ȣ���ʵʱӦ����Ҫע�������
=====================


��������а�һ��ʵʱ�Ļ���Adobe Air��ʵʱ��Ƶ�������porting��Android�ϡ�ԭ��PC�汾����ʱ��Ƶ�������ܺã�����ת��Android�Ϻ���3G�����ϲ��Է�����Ƶ�����Ƚϲ����Air�������������ͨ��RTMP��һ����TCP��Э������ͨ�ģ��ڽ������Ĺ�������һЩ����TCP��СС���֡�

----------


#### 3G�²��Գ������
��3G�����²��Ե�ʱ���������豸��������һ�����ٲ��Ե�APP���ó���ʱ������������4.5M����1.6M���ң���WCDMA��˵����һ���ȽϺõ����֣������ǵķ�������������Ƶ��������Ҫ320K�Ĵ���͹��ˡ�Ȼ��ʵ��ͨ��ʱ����Ƶ����Ƶ�������ǳ�����˫��������Ƶ��������Ƶ���������Ƚϲ��

#### ��������ץ��
> **NOTE:**
> ��Ҫע��ץ����׼ȷ�����⡣�ڷ������������tcpdumpץ�����ر�������ƵʵʱӦ�õ�ʱ��������������tcpdump�����ĵײ����ܻ������������buffer�����ʹ�������ļ�����������������wireshark������ʱ��ῴ���Ķ��������ǲ�׼ȷ�ġ���������ο�[tcpdumpץ����ʧ����](http://wenku.baidu.com/view/74b3166e1eb91a37f1115cf6.html)��

�ڷ���ץ���İ�ʱ���ǿ��������Ķ���������ͼ��
![](/media/pic/14/140120-packetloss.jpg)

������ԵĽ��

#### 3G������TCP����

���ֲ��������ó�����Ҫ������**TCP��WCDMA3G�µ�����Զ�ﲻ��������ֵ**����Ϊ�����ᵼ��TCP����Ϊ������ӵ������˫����С�շ����ڣ��������١�
��ͼ������ʵ���TCP���١�
![](/media/pic/14/140120-1.png)
������һ��ά������ô˵�������ģ�
[TCP_over_wireless_networks](http://en.wikipedia.org/wiki/Transmission_Control_Protocol#TCP_over_wireless_networks)
{% highlight objc %}
TCP has been optimized for wired networks. Any packet loss is considered to be the result of network congestion and the congestion window size is reduced dramatically as a precaution. However, wireless links are known to experience sporadic and usually temporary losses due to fading, shadowing, hand off, and other radio effects, that cannot be considered congestion. After the (erroneous) back-off of the congestion window size, due to wireless packet loss, there can be a congestion avoidance phase with a conservative decrease in window size. This causes the radio link to be underutilized. Extensive research has been done on the subject of how to combat these harmful effects. Suggested solutions can be categorized as end-to-end solutions (which require modifications at the client or server),[38] link layer solutions (such as RLP in cellular networks), or proxy based solutions (which require some changes in the network without modifying end nodes).
{% endhighlight %}

[�ο�3G�ı������](http://en.wikipedia.org/wiki/3g)
{% highlight objc %}
HSPA is an amalgamation of several upgrades to the original W-CDMA standard and offers speeds of **14.4 Mbit/s** down and **5.76 MBit/s** up. HSPA is backwards compatible with and uses the same frequencies as W-CDMA.
{% endhighlight %}
ע�������ٲ�����������������ģ�����150M��WiFiʵ�����ݴ����ٶȳ�����80�ס�3G���ĵ�������ܸ��ࡣ

#### ��θĽ�

**������**
�����ʵʱͨ�ų��򶼻������ӽ���ǰ�����������Դ������������ڴ�ͳ�������ⲻ�󣨻Ჿ���ܵ�tcp slow start��Ӱ�죩��������3G�£��⼸�������������������ٶȻ���ߣ�����ж������������ٶȻ���͡�

������3G�µ�Ӧ�ñ��������ӽ�����ʵʱ���ͨ����������������ӳ����ӵ����Ҫʵʱ������Ƶ�ֱ����Ա�֤������

��һ�ּ򵥰취���ӳ�һ��ʼ�Ĵ������ʱ�䡣����˵��ʮ�롣��������Skype�ĶԱȲ����з��ִӲ��ŵ��Է�ʵ�������нϳ��ӳ٣����м��п��ܾ����ڲ����


**UDP**
ʹ�û���UDP�Ĵ���Э����ԴӸ����Ͻ���������⡣
----
