---

copyright:
  years: 2015, 2017
lastupdated: "2017-06-01"

---

{:new_window: target="\_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 시작하기 튜토리얼
{: #getting-started-with-iotp}

이 {{site.data.keyword.iot_full}} 시작하기 튜토리얼에서 IoT 디바이스를 {{site.data.keyword.iot_short_notm}}에 연결하고 실시간 데이터를 탐색하도록 분석을 설정합니다.
{:shortdesc}

<div id="prerequisites"></div>

## 시작하기 전에
{: #prereqs}

[Bluemix 계정 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://console.bluemix.net/registration/){: new_window},
{{site.data.keyword.iot_short_notm}} 서비스의 인스턴스 및 다음 요구사항을 충족하는 디바이스가 필요합니다. 

*	디바이스가 HTTP 또는 MQTT 프로토콜을 사용하여 통신할 수 있어야 합니다. 

* 디바이스 메시지가 {{site.data.keyword.iot_short_notm}} 메시지 페이로드 요구사항을 준수해야 합니다. 

자세한 정보는 [Watson IoT Platform에서 디바이스 개발](/docs/services/IoT/devices/device_dev_index.html)을 참조하십시오. 

## 1단계: 디바이스 등록

{{site.data.keyword.iot_short_notm}} 대시보드에서 한 번에 하나씩 디바이스를 추가하거나 [Watson IoT Platform  API ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://docs.internetofthings.ibmcloud.com/apis/swagger/v0002/org-admin.html#!/Device_Bulk_Configuration/post_bulk_devices_add){: new_window}를 사용하여 여러 디바이스를 추가할 수 있습니다. 

{{site.data.keyword.iot_short_notm}} 대시보드에서 디바이스를 추가하려면 다음을 수행하십시오.

1. {{site.data.keyword.Bluemix_notm}} 콘솔의 {{site.data.keyword.iot_short_notm}} 서비스 세부사항 페이지에서 **실행**을 클릭하십시오. 

    {{site.data.keyword.iot_short_notm}} 웹 콘솔은 새 브라우저 탭에서 다음 URL을 엽니다. 

    ```
 https://org_id.internetofthings.ibmcloud.com/dashboard/#/overview
 ```

    여기서 *org_id*는 [{{site.data.keyword.iot_short_notm}} 조직 ](iotplatform_overview.html#organizations){: new_window}의 ID입니다. 

2. 개요 대시보드의 메뉴 분할창에서 **디바이스**를 선택한 다음 **디바이스 추가**를 클릭합니다.

3. 추가하는 디바이스의 디바이스 유형을 작성합니다.

    {{site.data.keyword.iot_short_notm}}에 연결된 각 디바이스는 디바이스 유형과 연관되어야 합니다. 디바이스 유형은 공통 특성을 공유하는 디바이스 그룹입니다.

    1. **디바이스 유형 작성**을 클릭합니다.
    2. 디바이스 이름(예: `my_device_type`) 및 디바이스 유형에 대한 설명을 입력합니다.
    
        > **참고:** 디바이스 유형 이름은 36자 이하여야 하며 영숫자 문자(a-z, A-Z, 0-9) 및 다음 문자(`_`, `.`, `-`)만 포함할 수 있습니다.

    3. 선택사항: 디바이스 유형 속성 및 메타데이터를 입력합니다.

        속성과 메타데이터는 나중에 추가하고 편집할 수 있습니다.
        {: tip}

4. **다음**을 클릭하여 선택한 디바이스 유형의 디바이스를 추가하는 프로세스를 시작합니다.

5. 디바이스 ID(예: `my_first_device`)를 입력합니다.

    디바이스 ID는 {{site.data.keyword.iot_short_notm}} 대시보드에서 디바이스를 식별하는 데 사용하고 디바이스를 {{site.data.keyword.iot_short_notm}}에 연결하는 데도 필요한 매개변수입니다.

    > **참고:** 디바이스 유형 이름은 36자 이하여야 하며 영숫자 문자(a-z, A-Z, 0-9) 및 다음 문자(`_`, `.`, `-`)만 포함할 수 있습니다.

    네트워크 연결 디바이스의 경우, 구분하는 콜론이 없는 디바이스 MAC 주소가 디바이스 ID가 될 수 있습니다.

5. **다음**을 클릭하여 프로세스를 완료합니다.

6. 인증 토큰을 제공하거나 자동으로 생성된 토큰을 허용하십시오. 고유 토큰을 작성하도록 선택하는 경우, 길이는 8 - 36자이고 영숫자 문자와 다음 특수 문자(`_`, `.`, `!`, `&`, `@`, `?`, `\*`, `+`, `(`, `)`, `-`)로만 구성되어야 합니다. 

    토큰에는 반복된 문자 시퀀스, 사전 단어, 사용자 이름 또는 기타 사전 정의된 시퀀스가 포함되지 않아야 합니다.

7. 요약 정보가 올바른지 확인한 다음 **추가**를 클릭하여 연결을 추가합니다.

8. 디바이스 정보 페이지에서 다음 세부사항을 복사하고 저장합니다.

    * 조직 ID
    * 디바이스 유형
    * 디바이스 ID
    * 인증 방법
    * 인증 토큰

    {{site.data.keyword.iot_short_notm}}에 연결하도록 디바이스를 구성하려면 조직 ID, 디바이스 유형, 디바이스 ID 및 인증 토큰이 필요합니다. 

## 2단계: {{site.data.keyword.iot_short_notm}}에 디바이스 연결

1. MQTT 메시징을 위한 디바이스를 설정하고 조직 ID, 디바이스 유형, 디바이스 ID 및 인증 토큰을 사용하여 인증합니다. 

2. MQTT 프로토콜을 사용하여 {{site.data.keyword.iot_short_notm}} 조직에 디바이스 메시지를 보냅니다.

    디바이스에 연결할 때 다음 정보가 필요합니다.

    * URL: *org_id*.messaging.internetofthings.ibmcloud.com

      여기서 *org_id*는 {{site.data.keyword.iot_short_notm}} 조직의 ID입니다.

    * 포트:
      * 1883
      * 8883(암호화됨)
      * 443(websockets)
    * 디바이스 ID: d:*org_id:device_type:device_id*
    * 사용자 이름: use-token-auth
    * 비밀번호: *인증 토큰*
    * 이벤트 주제 형식: iot-2/evt/*event_id/fmt/format_string*

      여기서 *event_id*는 {{site.data.keyword.iot_short_notm}}에 표시된 이벤트 이름을 지정하며, *format_string*은 이벤트의 형식(예: JSON)입니다.

    * 메시지 형식: JSON

  자세한 정보는 [디바이스용 MQTT 연결](/docs/services/IoT/devices/mqtt.html)을 참조하십시오. 

## 3단계: 디바이스 데이터를 계속 추적하기 위한 보드 및 카드 작성

보드 및 카드를 사용하여 디바이스 데이터의 개요를 신속하게 파악하고 이해하기 위해 하나 이상의 디바이스의 데이터 세트 값을 표시하는 그래픽을 볼 수 있습니다. 

1. {{site.data.keyword.iot_short_notm}} 대시보드에서 **새 보드 작성**을 클릭하십시오.

2. 보드에 대한 이름 및 설명을 입력하십시오. 

3. **다음**을 클릭한 후에 **작성**을 클릭하십시오.

4. 방금 작성한 보드를 클릭한 후에 **새 카드 추가**를 클릭하십시오. 카드 유형으로 디바이스를 선택하십시오. 사용자가 선택할 수 있는 시각화 옵션에 대해 다음 표에서 설명합니다. 

| 유형 | 표시되는 데이터        |
|---------------|---------------|
| 일반 시각화 | 하나 이상의 데이터 세트의 값입니다. 소형 테이블에서 최대 세 개의 데이터 점 값을 보려면 대형 위젯 크기를 선택하십시오.  |
| 선형 차트 | 실시간 화면 이동 차트에서 하나 이상의 데이터 세트입니다. 설정 메뉴를 사용하여 데이터 범위 및 보관, 그래프의 룩앤필 등을 설정할 수 있습니다.  |
| 막대형 차트 | 레이블 지정된 막대로 표시된 데이터 세트 값입니다. 설정 메뉴를 사용하여 가로 또는 세로 막대 방향을 토글할 수 있습니다.  |
| 도넛형 차트 | 원형으로 표시된 둘 이상의 데이터 세트입니다.  |
| 값 | 하나 이상의 데이터 세트의 원시 값입니다.  |
| 게이지 | 게이지로 표시된 데이터 세트 값입니다. 설정 메뉴를 사용하여 하단, 중간 및 상단 데이터 범위에 대한 게이지 임계값을 선택사항으로 설정할 수 있습니다.  |
| 디바이스 특성 | 하나 이상의 디바이스에 대한 특정 특성입니다.  |
| 모든 디바이스 특성 | 하나 이상의 디바이스에 대한 모든 특성입니다.  |
| 디바이스 목록 | 여러 디바이스를 모니터하기 위한 목록입니다. 목록은 다른 카드에 대한 데이터 소스로 사용할 수 있습니다.  |
| 디바이스 정보 | 단일 디바이스에 대한 기본 정보입니다.  |
| 디바이스 맵 | 디바이스 목록에서 디바이스의 위치입니다.  |

{: caption="표 1. 시각화 옵션" caption-side="top"}

## 4단계: 디바이스 유형 스키마 작성

이 지점에서 디바이스 유형 스키마를 작성하고 디바이스 특성을 맵핑한 후에 맵핑된 디바이스 특성에서 데이터 점을 기반으로 트리거되는 규칙을 작성하십시오. 

1. {{site.data.keyword.iot_short_notm}} 대시보드에서 **디바이스 > 스키마 관리**로 이동해서 **스키마 추가**를 클릭하십시오.

2. 메시지 스키마와 연관시킬 디바이스 유형을 선택하십시오. 디바이스 유형에 하나의 스키마만 정의할 수 있습니다.

3. **특성 추가**를 클릭하고 하나 이상의 특성을 추가하십시오.

    연결된 디바이스에서 특성을 선택하거나, 기존 특성을 수정하거나 결합하는 가상 특성을 작성하거나, 수동으로 특성을 추가할 수 있습니다.

    사용 가능한 특성은 디바이스에서 전송한 메시지의 페이로드에 정의됩니다.
    {: tip}

    * 특성을 수동으로 추가하려면 **수동 탭**을 선택하고 다음 특성 세부사항을 정의하십시오. 
        * 이름
        * 데이터 유형
        * 특성
        * 데이터 단위(선택사항)
        * 소수점 자리(선택사항)

    * 가상 특성을 작성하려면 **가상 특성** 탭을 선택하고 다음 특성 세부사항을 정의하십시오. 
        * 이름
        * 데이터 유형
        * 특성
        * 계산
        * 데이터 단위(선택사항)
        * 소수점 자리

    * 연결된 디바이스에서 특성을 선택하려면 **연결에서** 탭을 선택한 후에 스키마에 추가할 하나 이상의 특성을 선택하십시오. 선택한 특성이 추가되고 설명이 특성의 이름으로 설정됩니다. 

4. 특성을 작성하려면 **완료**를 클릭하십시오. 

## 5단계: 규칙 및 조치 작성

규칙은 실시간 디바이스 데이터를 사전 정의된 임계값이나 기타 특성 데이터와 일치시켜서 조건이 충족되면 경보를 트리거하는 조건 기반의 의사결정 지점입니다. {{site.data.keyword.iot_short_notm}} 대시보드에 표시되는 경보 외에도 규칙이 트리거될 때 비즈니스 로직을 실행하기 위한 하나 이상의 조치를 추가할 수 있습니다. 

1. {{site.data.keyword.iot_short_notm}} 대시보드에서 **규칙**으로 이동해서 **클라우드 규칙 작성**을 클릭하십시오.

2. 규칙의 이름과 설명을 입력하고 그 규칙이 적용되는 디바이스 유형을 선택하고 **다음**을 클릭하십시오.

3. 규칙 로직을 설정하려면 규칙에 대한 트리거로 사용할 하나 이상의 IF 조건을 추가하십시오. 

    병렬 행에서 조건을 추가하여 이를 OR 조건으로 적용하거나, 순차 열에서 조건을 추가하여 이를 AND 조건으로 적용할 수 있습니다. 다음 예를 살펴보십시오.

      * 매개변수 값이 지정된 값보다 큰 경우 단순 규칙이 경보를 트리거할 수 있음: 조건 = `temp_cpu>80`
      * 임계값의 조합이 충족될 때 더 복잡한 규칙이 트리거할 수 있음: 조건 = `temp_cpu>60 AND cpu_load>90`

    두 개의 특성을 비교하는 조건을 트리거하거나 AND를 사용하여 순차적으로 결합된 둘 이상의 특성 조건을 트리거하려면 동일한 디바이스 메시지에 트리거링 데이터 점을 포함하십시오. 데이터가 둘 이상의 메시지에서 수신되면, 조건 또는 순차 조건이 트리거되지 않습니다.
    {: tip}

4. 규칙에 대한 조건부 트리거 요구사항을 구성하십시오.

    일정 기간 동안 규칙에 대해 트리거되는 경보의 수를 제어하기 위해 조건부 트리거 요구사항을 사용할 수 있습니다. 조건부 트리거링은 규칙의 모든 조건에서 작동합니다. 예를 들어, 규칙에 OR을 사용하여 설정된 다섯 개의 병렬 조건이 있으면 true인 각 조건은 조건부 트리거 개수에 포함됩니다. 

      1. 규칙 편집기에서 기본 **조건이 충족될 때마다 트리거** 링크를 클릭하여 빈도 설정 요구사항 대화 상자를 여십시오. 
      2. 규칙에서 사용하려는 조건부 트리거를 선택하고 구성하십시오. 

        * 조건이 충족될 때마다 트리거
        * M *단위 시간*에 조건이 N번 충족되면 트리거

5. 규칙 조건이 충족되면 발생하는 하나 이상의 조치를 작성하거나 선택하십시오.

    예를 들어, 조치를 사용하여 이메일을 발송하거나 웹훅을 게시할 수 있습니다. 

6. 선택사항: 규칙에 대한 경보 우선순위를 선택하십시오.

    우선순위는 **보드 > 규칙 기반 분석** 보드에서 표시되는 경보를 분류하는 데 사용됩니다. 기본 우선순위는 '낮음'입니다.

7. **저장**을 클릭하여 활성화 없이 저장하거나 **활성화**를 클릭하여 규칙을 저장하고 활성화하십시오. 

    규칙을 활성화하는 경우, 조건이 충족되면 경보가 **규칙 기반 분석** 보드에 추가되며 규칙 조치가 실행됩니다. 

## 다음 단계

실시간 및 히스토리 디바이스 데이터를 이용하기 위해 고유 앱을 작성해서 연결하여 데이터 분석 기능을 확장합니다.

  * 디바이스와 앱을 통합해서 연결하기 위해 코드를 빌드하도록 도구에 대한 [클라이언트 라이브러리](/docs/services/IoT/iot_platform_client_lib.html)를 체크아웃하십시오. 

  * 고급 분석을 사용자의 연결된 디바이스와 앱에 임베드하기에 대한 추가 튜토리얼은 [Watson IoT Platform 레시피 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://developer.ibm.com/recipes/tutorials/category/internet-of-things-iot/){: new_window}을 탐색하십시오. 
