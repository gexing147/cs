��Ƴ���
==============================================
ר�������ҵ���������칤��,��󻯷���Ա����ͨ�ͽ���.

1.���ݰ�ȫ,����ֻ����������.

2.���͹�˾�Ի�������������,�������Ϳ�������ʹ��,֧����������.

3.���Ի�����,��˾����������Ϣ�����пͻ���,��¼��Ĭ������ͬ�¶�����ĺ���,�ȵ�.


��ƽ׶�
==============================================
��һ�׶�

1.server ��������,��linux��ʹ��c����

2.linux �����пͻ��˿���

3.linux ͼ�οͻ��˿���

�ڶ��׶�

1.server����cs.conf�ļ�����

3.ʵ���ļ�ת��

4.windows ͼ�οͻ��˿���

5.�ͻ���ʵ����Ļ��ͼ

�����׶�

1.android ͼ�οͻ��˿���

2.ios ͼ�οͻ��˿���


server����
==============================================
1.�û���֤

2.���ѹ�ϵ�ж�

3.����client�ĺϷ�����

4.ͬһ�������ж�

5.������Ϣת��(֧�ֶԷ�����,��������)

6.�ļ�ת��(֧�ֶԷ�����,��������)

7.���͹���(֧�ֶԷ�����,��������)


serverģ��
==============================================
0.���������ļ� cs.conf

1.�����¼���Ӧ,ʹ�� ������ + select

2.�¼������߼�

3.���ݿ����,ʹ�� sqlite


server���л���
==============================================
CentOS release 6.4

download: http://mirrors.163.com/centos/6.4/isos/


client����
==============================================
1.ע��

2.��¼

3.�鿴�����û�������״̬(֧�ַ���)

4.��Ӻ���

5.ɾ������

6.����������Ϣ

7.����������Ϣ

8.�鿴�����¼

9.ɾ�������¼

10.���չ�����Ϣ

11.�����ļ�

12.��Ļ��ͼ

13.Ⱥ�齨


client֧��ƽ̨
==============================================
linux / windows / android / ios


ͨ��Э��  client������ �� server�Ļ�Ӧ
==============================================
client������

ע���û�		:0:troy:troy:::

�����û�		:1:::::

��½			:2:troy:troy:::

�˳�			:3:::::

�鿴�����û�	:4:::::

��Ӻ���		:5:troy:_:ivy::

ɾ������		:6:troy:_:ivy::

���������		:7:troy:_:zyy:nihao,zyy:20131117100404

				:7:zyy:_:troy:nihao,troy:20131117100404

�鿴�����¼	:8:troy:_:ivy::

ɾ�������¼	:9:troy:_:ivy::


server�Ļ�Ӧ

10	δ֪��������

10	�ɹ�(תΪ��¼״̬)

11	�����ʧ��

12	�û����Ѵ���

13	���û�������

......


���ݿ�(cs.db)���
==============================================
1.ȫ���û��� �� �Ƿ�����״̬ �ı�

create table users(id integer primary key, name text, passwd text, online text, fd integer);

insert into users(name, passwd, online, fd) values('root', 'root', 'off', -1);

insert into users(name, passwd, online, fd) values('troy', 'troy', 'off', -1);

2.����Ϊ�û��� ���û������к���

create table troy(id integer primary key, name text, log_type integer);

insert into troy(name, log_type) values('ivy', -1);

insert into troy(name, log_type) values('cy', -1);

insert into troy(name, log_type) values('jdy', -1);

3.����Ϊ�û���-�����û��� ��������¼

create table troy_ivy(id integer primary key, name text, content text, datetime text);

insert into troy_ivy(name, content, datetime) values('ivy', 'hello,ivy', '20131117100404');

insert into troy_ivy(name, content, datetime) values('troy', 'hello,troy', '20131117100504');


�����
==============================================
select troy.name, users.online from troy,users where troy.name=users.name;	//����ѯ

select count(*) from sqlite_master where type='table' and name='user';		//���Ƿ����

create table users(id integer primary key, name text, passwd text, online text);

insert into users(id, name, passwd, online) values(1, 'root', '123', 'off');

select * from user where name='troy' and passwd='troy';

update employee set age=25, name='dongqiang' where name='dq';

delete from employee where id=5 or name="cj";

drop table troy_ivy;		//ɾ����


����
==============================================
cs	communication server

cc	communication client

db	database


need
==============================================
yum install sqlite.i686


how to use?
==============================================
root@cs# make sql	/*��ʼ�����ݿ�*/

root@cs# make

root@cs# ./cs       /* default port: 8888 */

root@cs# ./cc/cc

[8.16:39:21.476]:cc->src/cc_client.c->main:00044 --> connect 127.0.0.1 at PORT 8888 success.

:0:troy:troy:::		/* ע�����û� */

[8.16:39:25.779]:cc->src/cc_client.c->main:00056 --> buf=:1:troy:troy:::

[8.16:39:25.783]:cc->src/cc_client.c->main:00072 --> buf=:ivy-on:cy-off:jdy-on