---

copyright:

  years: 1994, 2018

lastupdated: "2018-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:new_window: target="_blank"}


# 시스템 보호
{: #customerportal_protsys}

시스템 보호를 통해 불필요한 인터럽트 없이 시스템을 원활하게 실행할 수 있습니다.

## 사설 네트워크 사용
{: #cp_bpuseprivnet}

{{site.data.keyword.BluSoftlayer_notm}} 인프라 사설 네트워크 사용하여 가능한 가장 안전한 환경에서 디바이스를 관리할 수 있습니다. 가능하면 VPN 연결을 사용하여 디바이스와 상호작용하고 시스템이 사설 네트워크를 통해 통신하도록 네트워크 스패닝을 사용으로 설정하십시오. 사설 네트워크에 액세스하려면 [사용자 목록 ![외부 링크 아이콘](../icons/launch-glyph.svg)](https://control.softlayer.com/account/user/list){:new_window}에서
사용자의 VPN 액세스를 편집하십시오. [가상 사설망(VPN) ![외부 링크 아이콘](../icons/launch-glyph.svg)](http://www.softlayer.com/vpn-access){:new_window} 목록을 사용하여 다양한 VPN 옵션 중 하나에 연결하십시오.

VPN 연결 사용에 대한 자세한 정보는 [VPN 정보](/docs/infrastructure/iaas-vpn/about-vpn.html)를 참조하십시오.

### RDP, SSH 또는 제어 포트를 공용 네트워크에 두지 않음
{: #cp_bpnordpsshcponpubnet}

공용 네트워크는 여러 가지 측면에서 장점이 있지만, 개방형 포트를 통해 공용 네트워크에서 사용 가능한 상태로 남아 있는 경우와 같은 특정 측면으로 인해 시스템이 취약해질 수 있습니다. 공용 네트워크에서 RDP를 사용하지 않고 SSH를 제한하여 자체적으로 보호하십시오. 이 서비스가 공용 네트워크에서 사용 가능해야 하는 경우 RDP 또는 SSH를 사용자 정의 포트 번호로 이동하는 것을 고려해보십시오.

## 정기 백업을 통한 데이터 보호
{: #cp_bpsafedataregback}

데이터가 디바이스 외부에 안전하게 저장되도록 보장하고 유실된 경우에 이를 재로드할 수 있도록 백업을 스케줄하십시오.

{{site.data.keyword.BluSoftlayer_notm}} 인프라는 드라이브가 실패하거나 사용자로 인해 오류가 발생하는 경우 데이터를 검색할 수 있도록 다중 백업 솔루션을 제공합니다. 백업 솔루션에는 현재 NAS, EVault Backup 및 R1Soft CDP가 포함되며, 모두 다양한 스토리지 옵션에서 사용할 수 있습니다.
예를 들어, 다음 백업 서비스 중 1개를 선택하여 데이터를 안전한 위치에 저장할 수 있습니다.
  * EVault Backup은 자동화된 에이전트 기반 백업 시스템이며 "한 번만 설정하면 되는" 인기 있는 디바이스 관리용 솔루션입니다. 이는 플러그인을 통해 Exchange 및 SQL을 포함하는 Microsoft 소프트웨어와 호환 가능합니다. EVault 사용자는 EVault의 WebCC 웹 기반 애플리케이션을 통해 이 서비스와 상호작용합니다.
  * R1Soft CDP(Continuous Data Protection)는 사용자의 서버나 자체 관리되는 가상 머신에 설치될 수 있습니다. 모든 백업을 관리하기 위한 단일 인터페이스를 찾고 있는 경우에 사용할 수 있습니다. 사용자는 전용 관리 시스템을 통해 R1Soft CDP와 상호작용하며, 이는 에이전트가 가상 머신에 설치될 수 있도록 하고 추가 기능을 위한 데이터베이스 플러그인을 제공합니다.

 각 백업 솔루션의 자세한 정보는 [스토리지 ![외부 링크 아이콘](../icons/launch-glyph.svg)](http://www.softlayer.com/services/storagelayer/){:new_window} 페이지를 확인하고 데이터 백업의 자세한 정보는 [백업 서비스 시작하기](/docs/infrastructure/Backup/index.html)를 참조하십시오.

### 중복성이 있다고 간주하지 않음(수행하는 작업을 알고 있음)
{: #cp_bpknowredundant}

{{site.data.keyword.BluSoftlayer_notm}} 인프라는 이중 경로, 이중 전원 공급 장치 및 RAID 구성을 포함하여 여러 추가 기능 중복성을 제공합니다. 중복 환경에서 작업 중이며 장애가 있는 경우 보호될 수 있도록 이러한 기능 중 하나 이상을 프로비저닝했는지 확인하십시오.

### OS를 다시 로드하기 전에 정보가 백업되었는지 확인
{: #cp_bpnoperfOSwobackupconf}

운영 체제를 다시 로드하면 디바이스의 하드 디스크에서 모든 데이터가 제거됩니다. OS 다시 로드를 시작하기 전에 정보를 백업하고 정보가 유실되지 않도록 해당 백업이 성공했는지 확인하십시오. OS 다시 로드가 완료된 후에는 유실된 정보를 검색할 수 없습니다.

## ASM(Aaptec Storage Manager) 제거 안 함
{: #cp_bpsupdontremovasm}

 {{site.data.keyword.BluSoftlayer_notm}} 인프라는 ASM을 사용하여 RAID 배열 상태를 모니터합니다. 이 소프트웨어를 삭제하는 경우 지원 팀에서 디바이스를 모니터할 수 업습니다. 디바이스에서 ASM을 제거하면 디바이스에 대한 RAID 장애 알림을 사용할 수 없고 자동 알림 시스템을 통한 장애 알림을 받을 수 없게 됩니다.
