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

����server���л���

CentOS release 6.4


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
linux

windows

android

ios


ͨ��Э��  client������ �� server�Ļ�Ӧ
==============================================

:request_type:username:passwd:whoname:content:request_time

client��server���͵���������

:0:name:passwd:::				//ע��

����:�ɹ�(תΪ��¼״̬)/ʧ��(ԭ��)

:1:troy:troy:::20131117100404

:1:name:passwd:public ip:private ip:20131117100404	//��¼

����:�����б�

:2:::::						//�鿴�����û�

����:�û��б�

:3:::ivy::20131117100404			//��Ӻ���

����:�ɹ�/ʧ��

:4:::ivy::20131117100404			//ɾ������

����:�ɹ�/ʧ��

:5:::ivy:hello world.:20131117100404		//����������Ϣ

������Ϣ���Է� �����Լ��ͶԷ���log�ļ�

����:�ɹ�/ʧ��

:6:::ivy::					//�鿴�����¼

����:��ǰ�������¼

:7:::ivy::					//ɾ�������¼

����:�ɹ�/ʧ��

:8:::ivy:filename:20131117100404		//�����ļ�

����:�ɹ�/ʧ��


���ݿ�(cs.db)���
==============================================

1.ȫ���û��� �� �Ƿ�����״̬ �ı�

create table users(id integer primary key, name text, passwd text, online text);

insert into users(id, name, passwd, online) values(1, 'root', '123', 'off');

insert into users(id, name, passwd, online) values(2, 'troy', '456' 'off');

2.����Ϊ�û��� ���û������к���

create table troy(id integer primary key, name text, log_state int);

insert into troy(id, name, online) values(1, 'ivy', 0);

insert into troy(id, name, online) values(2, 'cy', 1);

insert into troy(id, name, online) values(3, 'jdy', 2);

3.����Ϊ�û���-�����û��� ��������¼

create table troy_ivy(id integer primary key, content text, datetime text);

insert into troy_ivy(id, content, datetime) values(1, 'hello ivy', '20131117100404');

insert into troy_ivy(id, content, datetime) values(2, 'hello troy', '20131117100504');


�����
==============================================

select count(*) from sqlite_master where type='table' and name='user';		//���Ƿ����

create table users(id integer primary key, name text, passwd text, online text);

insert into users(id, name, passwd, online) values(1, 'root', '123', 'off');

select * from user where name='troy' and passwd='troy';

update employee set age=25, name='dongqiang' where name='dq';

delete from employee where id=5 or name="cj";



cs
==============================================
communication server

use c language on linux

need
==============================================
yum install sqlite.i686

how to use?
==============================================
root@cs# make

root@cs# ./cs       /* default port: 8888 */

root@cs# ./cs/cc
