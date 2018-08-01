CaaS Service broker for PaaS-TA
==================
CaaS ���� ���Ŀ�� CaaS ���񽺸� �Ľ�-Ÿ(PaaS-TA) ���񽺷� �����մϴ�.

�� ���� ���Ŀ�� CaaS ���� �� �����Ƽ��(Kubernetes)�� �����ϰ� ������, Ŭ���� ��Ʈ�ѷ��� ���� ���Ŀ ���� v2 ���� API�� �����ݴϴ�. 
�� API�� Ŭ���� ��Ʈ�ѷ� API�� ȥ���Ǿ�� �ȵ˴ϴ�.

�� ���Ŀ���� CaaS ���� Ȥ�� CaaS ����� ���ԵǾ� ���� �ʽ��ϴ�.
��� CaaS ������ ���񽺸� �����ϴ� CaaS �ڹ� ���Ŀ�� �����ϴ� ���� �ǹ��մϴ�.

CaaS ���� ���Ŀ�� CaaS ������ PaaS-TA(Ŭ���� �Ŀ�帮)���� ���񽺸� �����ϴ� ���� ���ϸ�, ���� �����Ͽ� ����Ǵ� CaaS ���� �������α׷��� ������ �������� �ʽ��ϴ�.

�� ���Ŀ�� �����ϴ� CaaS ���� �۾��� ������ �����ϴ�.
- CaaS ������ īŻ�α� ���
- CaaS �ν��Ͻ� ���κ����� ���� (���ӽ����̽� �� ���� ����)
- CaaS �ν��Ͻ� ���κ����� �÷��� ����
- CaaS �ν��Ͻ� ���κ����� ���� (���� �� ���ӽ����̽� ����)
�� ���Ŀ������ CaaS ���񽺿� ���� ���ε�/����ε��� �������� �ʽ��ϴ�.
[������ ���� ���̵�](https://github.com/PaaS-TA/Documents-PaaSTA-1.0/blob/master/Development-Guide/ServicePack_develope_guide.md)�� API ���� ���̵带 �����Ͻø� ��Ű���Ŀ� ���, ������ ���߿� ���� �ڼ��� �� �� �ֽ��ϴ�.

--------------------
�� ���Ŀ�� �ҽ��ڵ带 ����ϱ� ���� ȯ���� ������ �����ϴ�.
- ���� ȯ�� : Java 8 + Gradle 4.x
- ������ ��Ű��
  - PaaS-TA Service Java broker (>= Java 8)
  - Spring boot 1.5.14
    > Spring boot JPA \
    > Spring boot Web \
    > Spring boot Security \
    > Spring boot Session core \
    > Spring boot Test
  
  - MySQL JDBC Driver (Runtime Provider)
  - Jayway Json-Path

----------

������ ��� ��� (���� ȯ��)

- Catalog ��ȸ (GET) : http://localhost:8888/v2/catalog
  - Header
    > Authorization : Bearer type \
    > X-Broker-Api-Version : 2.4 \
    > Content-Type : application/json
  
  - Body : None

- ���� �ν��Ͻ� ���� (PUT) : 
  - Header
    > Authorization : Bearer type \
    > X-Broker-Api-Version : 2.4 \
    > Content-Type : application/json \
    > Accept: application/json
  
  - Body
    > { \
    >   "service_id": \<service-id-string>, \
    >   "plan_id": \<plan-id-string>, \
    >   "organization_guid": \<organization-guid-string>, \
    >   "space_guid": \<space-guid-string>, \
    >   "parameters": { "userName": \<user-name-in-caas-service> }\
    > }


- ���� �ν��Ͻ� ���� (PATCH) : 
  - Header
    > Authorization : Bearer type \
    > X-Broker-Api-Version : 2.4 \
    > Content-Type : application/json 
  - Body
    > { \
    >   "plan_id": \<plan-id-string>, \
    >   "service_id": \<service-id-string> \
    > } 


- ���� �ν��Ͻ� ���� (DELETE) : 
  - Header
    > Authorization : Bearer type \
    > X-Broker-Api-Version : 2.4 \
    > Content-Type : application/json 
  - Body : None

