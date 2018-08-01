Kubernetes Service broker for PaaS-TA
==================
�����Ƽ��(Kubernetes) ���� ���Ŀ�� �����Ƽ�� ���񽺸� �Ľ�-Ÿ(PaaS-TA) ���񽺷� �����մϴ�.
�� ���� ���Ŀ�� Ŭ���� ��Ʈ�ѷ��� ���� ���Ŀ ���� v2 ���� API�� �����ݴϴ�.
�� API�� Ŭ���� ��Ʈ�ѷ� API�� ȥ���Ǿ�� �ȵ˴ϴ�.

�� ���Ŀ���� �����Ƽ�� ������ ���ԵǾ� ���� �ʽ��ϴ�.
��� �����Ƽ�� ������ ���񽺸� �����ϴ� �����Ƽ�� �ڹ� ���Ŀ�� �����ϴ� ���� �ǹ��մϴ�.

�����Ƽ�� ���� ���Ŀ�� �����Ƽ�� ������ OpenPaas(Ŭ���� �Ŀ�帮)���� ���񽺸� �����ϴ� ���� ���ϸ�, ���� �����Ͽ� ����Ǵ� �����Ƽ�� ���� �������α׷��� ������ �������� �ʽ��ϴ�.

�� ���Ŀ�� �����ϴ� �����Ƽ�� ���� �۾��� ������ �����ϴ�.
- �����Ƽ�� ������ īŻ�α� ���
- �����Ƽ�� �ν��Ͻ� ���κ����� ���� (���ӽ����̽� �� ���� ����)
- �����Ƽ�� �ν��Ͻ� ���κ����� �÷��� ����
- �����Ƽ�� �ν��Ͻ� ���κ����� ���� (���� �� ���ӽ����̽� ����)
�� ���Ŀ������ �����Ƽ�� ���񽺿� ���� ���ε�/����ε��� �������� �ʽ��ϴ�.
[������ ���� ���̵�](https://github.com/OpenPaaSRnD/Documents-PaaSTA-1.0/blob/master/Development-Guide/ServicePack_develope_guide.md)�� API ���� ���̵带 �����Ͻø� ��Ű���Ŀ� ���, ������ ���߿� ���� �ڼ��� �� �� �ֽ��ϴ�.

==================
�� ���Ŀ�� �ҽ��ڵ带 ����ϱ� ���� ȯ���� ������ �����ϴ�.
- ���� ȯ�� : Java 8 + Gradle 4.x
- ������ ��Ű��
-- OpenPaaS Service Java broker (>= Java 8)
-- Spring boot 1.5.14
  > Spring boot JPA
  > Spring boot Web
  > Spring boot Security
  > Spring boot Session core
  > Spring boot Test
-- MySQL JDBC Driver (Runtime Provider)
-- Jayway Json-Path

==================

������ ��� ��� (���� ȯ��)

- Catalog ��ȸ (GET) : http://localhost:8888/v2/catalog
-- Header
  > Authorization : Bearer type
  > X-Broker-Api-Version : 2.4
  > Content-Type : application/json
-- Body : None

���� ���� ��� ��� (���� ȯ��)

- ���� �ν��Ͻ� ���� (PUT) : 
-- Header
  > Authorization : Bearer type
  > X-Broker-Api-Version : 2.4
  > Content-Type : application/json
  > Accept: application/json
-- Body
  > {
  >   "service_id": <service-id-string>,
  >   "plan_id": <plan-id-string>,
  >   "organization_guid": <organization-guid-string>,
  >   "space_guid": <space-guid-string>
  > }


- ���� �ν��Ͻ� ���� (PATCH) : 
-- Header
  > Authorization : Bearer type
  > X-Broker-Api-Version : 2.4
  > Content-Type : application/json
-- Body
  > {
  >   "plan_id": <plan-id-string>,
  >   "service_id": <service-id-string>
  > }


- ���� �ν��Ͻ� ���� (DELETE) : 
-- Header
  > Authorization : Bearer type
  > X-Broker-Api-Version : 2.4
  > Content-Type : application/json
-- Body : None


