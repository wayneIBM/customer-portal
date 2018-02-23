---

copyright:

  years: 1994, 2018

lastupdated: "2018-01-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:new_window: target="_blank"}

# 환경 보안 및 스케일링
{: #cp_compsegapptierssecscal}

애플리케이션을 호스팅할 때 모든 시스템 관리자가 고려해야 할 가장 중요한 측면 중 두 가지는 애플리케이션의 보안 및 스케일링 가능성입니다.
{:shortdesc}

## 방화벽으로 시스템 보안
{: #cp_bpsecuresystem}

방화벽은 작동 여부를 확인하기 위해 수동으로 구성하고 사용해야 하는 디바이스에 대한 추가 기능 서비스입니다. 필요하지 않은 포트를 잠그고 사설 네트워크 기반 시스템이 시스템에 대한 외부 접근성을 추가로 관리할 수 있도록 공용 포트를 사용 안함으로 설정할 수 있습니다. 고객 포털의 주기적 취약성 스캔은 위험을 빨리 마이그레이션할 수 있도록 중요하거나 알 수 없는 보안 위험을 식별합니다.

### 방화벽 활성화
{: #cp_bpnofirewalbypass}

방화벽 구매는 시스템 보호의 시작이지만, 사용자를 보호하는 것은 아닙니다. 프로비저닝 후 방화벽은 **무시 모드**에 있으며 규칙 세트가 없습니다. 방화벽을 시작하고 실행하려면 원하지 않는 활동 차단을 시작할 수 있도록 규칙을 작성하고 방화벽을 활성화해야 합니다.


## 애플리케이션 계층을 세분화하여 환경 보안
{: #cp_copmsecenv}

논리적 애플리케이션 계층을 실제 인프라 계층으로 세분화하여 ACL(Access Control Lists) 사용을 통해 더 높은 수준의 보안을 제공할 수 있습니다. 애플리케이션 계층을 세분화할 때 고려할 가장 중요한 컴포넌트 중 하나는 각 계층으로 허용하는 트래픽과 발생 위치입니다. 이를 결정하려면 애플리케이션의 근본적인 작동 방식과 일반 사용자에게 요청된 컨텐츠를 제공하기 위해 서로 의존하는 서비스가 무엇인지 생각해야 합니다.

예를 들어, 웹프론트 및 데이터베이스 백엔드에 의존하는 2계층 애플리케이션을 사용하여 웹 서버에서 포트 80 및 443이(SSL을 사용 중인 경우) 인터넷에 열려 있는지 확인해야 합니다. 또한 인터넷까지 모든 포트를 잠그고 {{site.data.keyword.BluSoftlayer_full}} 인프라 사설 네트워크를 활용하여 VPN을 통해 서버를 관리하려고 할 수 있습니다. 이 시나리오에서는 데이터베이스 서버에서 공용 IP 주소를 바인드해제하고 웹 서버의 포트 1433(MSSQL용) 또는 3306({{site.data.keyword.mysql}}용) 전반에서 모든 트래픽을 데이터베이스 서버로 전달하려고 할 수 있습니다.  데이터베이스 서버는 웹 서버와 같이 사설 네트워크를 통해 관리될 수 있고 데이터베이스 서버의 소프트웨어 방화벽을 설정하여 웹 서버에서 특정 데이터베이스 포트까지 모든 트래픽을 잠글 수 있습니다.

이 방법으로 환경을 설정하여 인터넷에서 SSH 또는 RDP에 대한 액세스를 차단하고 데이터베이스에 대한 모든 인터넷 트래픽을 사용 안함으로 설정하여 보안 수준을 높입니다.  웹 서버가 손상되는 경우 웹 계층 및 데이터베이스 계층 간에 ACL을 작성하면 데이터베이스는 쉽게 손상되지 않습니다.

## 애플리케이션 계층을 세분화하여 환경 스케일링
{: #cp_copmscaleenv}

다중 계층 환경은 수직 또는 단일 호스트 아키텍처와 비교할 때 좀 더 쉬운 스케일링 가능성을 제공합니다. 추가 리소스가 필요한 서비스의 스케일링을 허용하여 애플리케이션을 좀 더 쉽게 스케일 확장할 수 있도록 다중 계층 환경을 설정할 수 있습니다. 예를 들어, 이전 시나리오에서 웹 서버가 과부화된 경우 간단히 다른 웹 서버를 배치하고, 사이트 또는 애플리케이션 데이터를 배치하고, 로드 밸런싱 또는 라운드 로빈 DNS를 설정하면 두 개의 웹 서버가 웹 로드를 분할할 수 있습니다. 라운드 로빈 DNS 또는 로드 밸런싱은 다중 웹 서버에서 수신 요청에 응답할 수 있도록 하여 환경에 대한 고가용성을 제공합니다.  단일 서버가 작동 중지되면 일반 사용자 요청을 처리하도록 다른 노드를 사용할 수 있습니다.

데이터베이스를 스케일 확장할 수도 있습니다. 예를 들어, {{site.data.keyword.mysql}} 데이터베이스를 사용한 하나의 옵션은 다른 실제 서버를 설정하고 {{site.data.keyword.mysql}} 마스터/슬레이브 복구 설정에서 ‘슬레이브’로 사용하는 것입니다.  모든 데이터베이스 쓰기를 ‘마스터’로 세분화하고 모든 읽기를 하나 이상의 ‘슬레이브’로 세분화하여 더 많은 로드를 지원하도록 데이터베이스를 스케일링할 수 있습니다.  또한 이 설정 유형은 사용자가 ‘슬레이브’의 상태를 ‘마스터’로 변경하도록 하여 고가용성의 레벨을 추가하고 {{site.data.keyword.mysql}} ‘마스터’ 노드가 중지되는 경우 읽기 및 쓰기 트래픽을 모두 라우트합니다.

이러한 사례는 환경을 보호하고 스케일링할 수 있는 많은 방법 중 일부에 불과합니다. 보안 또는 스케일링 가능성 관점에서 환경을 설계하기 위한 최상의 방법에 대해 질문이나 문의사항이 있는 경우 {{site.data.keyword.BluSoftlayer_notm}} 인프라의 영업 기술 팀이 도움을 드립니다.