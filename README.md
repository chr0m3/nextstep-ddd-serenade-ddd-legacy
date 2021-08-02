# 키친포스

## 요구 사항

Kitchen Pos 구현

도메인 종류

- `메뉴 그룹`
- `메뉴`
- `제품`
- `주문`
- `주문테이블`

요구 상세

메뉴그룹

- [ ]  메뉴그룹을 만들 수 있다.
    - [ ]  메뉴 그룹 생성에는 이름이 반드시 필요하다.
    - [ ]  메뉴 그룹은 이름과 메뉴 그룹을 특정하기 위한 고유한 값을 기준으로 만들어 진다.
    - [ ]  같은 이름의 메뉴 그룹을 생성 할 수 있다.
- [ ]  모든 메뉴 그룹을 조회할 수 있다.

제품

- [ ]  제품을 등록 할 수 있다.
    - [ ]  제품은 제품을 특정하기 위한 특정값과 가격, 이름으로 이루어 진다.
    - [ ]  제품의 가격과 이름은 반드시 존재 해야 한다.
    - [ ]  제품은 같은 이름의 제품이 존재 할 수 있다.
    - [ ]  제품의 가격은 0원 보다 커야 한다.
    - [ ]  제품 이름은 비속어로 이루어 질 수 없다.
- [ ]  제품의 가격은 변경 될 수 있다.
    - [ ]  제품의 가격은 0보다 작거나 비어있는 상태로 변경 될 수 없다.
    - [ ]  변경 요청 제품은 반드시 존재하는 제품 이어야 한다.
    - [ ]  변경 요청 제품은 이미 구성된 메뉴에 영향을 미치므로 제품이 포함된 메뉴의 가격은 0보다 커야하며, 0보다 작다면 해당 메뉴는 이용자에게 보여지면 안된다.
- [ ]  한 제품은 여러개의 메뉴에 속할 수 있다.
- [ ]  모든 제품을 조회 할 수 있다.

메뉴

- [ ]  메뉴를 등록 할 수 있다.
    - [ ]  메뉴는 메뉴를 특정하기 위한 고유한 값과 메뉴 이름, 가격, 
    메뉴에 속한 제품들로 이루어 진다.
    `메뉴에 속한 제품` 의 상세는 다음과 같다.
        - [ ]  메뉴는 한개 혹은 여러 종류의 제품으로 구성된다.
        - [ ]  메뉴에 구성된 한 제품의 수량은 한개 이상이다.
        - [ ]  메뉴 가격은 구성된 제품 가격의 합보다 클 수 없다.
    - [ ]  메뉴에는 가격과 제품이 반드시 책정 되어야 한다.
    - [ ]  메뉴 이름은 비속어로 이루어 질 수 없다.
    - [ ]  메뉴는 동일한 이름의 메뉴가 존재 할 수 있다.
    - [ ]  메뉴는 반드시 하나의 특정 메뉴그룹에 속한다.
- [ ]  메뉴 가격은 변경 될 수 있다
    - [ ]  메뉴의 가격은 0보다 작을 수 없다.
    - [ ]  `메뉴에 속한 제품`의 가격 합은 0보다 커야 한다.
- [ ]  메뉴는 display 속성에 의해 사용자에게 보여지거나 숨겨진다.
- [ ]  메뉴의 display 속성은 변경 될 수 있다.
    - [ ]  해당 메뉴는 실제 존재하는 메뉴여야 한다.
    - [ ]  메뉴의 가격이 0보다 작을 경우 해당 메뉴는 화면에 노출 될 수 없다.
- [ ]  모든 메뉴를 조회 할 수 있다.

주문

- [ ]  주문을 등록 할 수 있다.
    - [ ]  주문 등록에는 주문 타입이 필요하다.
    주문 타입은 반드시 필요하며,
    해당 타입은 `배달`, `테이크아웃`, `매장`내 식사로 이루어진다.
    - [ ]  주문 등록시에는 주문 아이템 목록이 반드시 필요하며 주문 목록은 한개 이상의 메뉴와 각 메뉴의 수량을 포함한다.

        주문 아이템 목록의 상세는 다음과 같다.

        - [ ]  주문 아이템 목록에 포함 된 메뉴들은 반드시 식당에 등록되어 있는 메뉴여야 한다.
        - [ ]  주문 아이템 목록의 메뉴의 가격과 식당에 등록되어 있는 메뉴의 가격이 다르면 안된다.
        - [ ]  주문 아이템 목록의 메뉴는 화면에 노출되어 있는 메뉴여야 한다. ( display 값 true )
        - [ ]  주문 타입이 매장 내 식사가 아닌 경우 메뉴의 수량이 0보다 작아서는 안된다.
- [ ]  주문에는 주문을 특정하기 위한 고유의 값이 있다.
- [ ]  주문에는 각 주문의 진행 상태를 나타내는 값들이 존재한다.
( `대기`, `수락`, `제공완료`, `배달중`, `배달완료`, `완료`)
- [ ]  주문 진행 상태 기본값은 `대기` 이며 주문 등록 과정을 통해 상태 값은 '대기' 로 설정 되어야 한다.
- [ ]  주문에는 주문이 등록된 날짜와 시간을 갖고 있다.
- [ ]  주문에는 배달 주소를 갖고 있다.
    - [ ]  주문 타입이 `배달` 일 경우 주문 등록 요청시 배달 주소를 반드시 포함해야 한다.
- [ ]  주문에는 주문 테이블 값을 갖고 있다.
    - [ ]  주문 타입이 `매장` 인 경우 주문 등록 요청시 주문 테이블 번호를 반드시 포함해야 하며, 해당 테이블은 비어있는 상태여야 한다.
- [ ]  주문을 `수락` 할 수 있다.
    - [ ]  주문을 `수락` 시 반드시 해당 주문은 존재하는 주문이어야 한다.
    - [ ]  주문을 `수락` 시 해당 주문의 상태는 대기중 이어야 한다.
    - [ ]  주문 `수락` 시 주문의 타입이 `배달`일 경우 해당 주문의 가격 합계를 구해 라이더 업체에 `주문 ID`, `가격 합계`, `배달 주소`와 함께 배달 요청을 보내야 한다.
    - [ ]  주문 `수락` 시 주문 상태를 `수락`으로 변경해야 한다.
- [ ]  주문을 고객에게 제공 할 수 있다.
    - [ ]  주문 `제공완료`시 해당 주문은 존재하는 주문 이어야 한다.
    - [ ]  주문 `제공완료`시 해당 주문의 상태는 `수락` 이어야 한다.
    - [ ]  주문 `제공완료`시 주문 상태는 `진행`으로 변경해야 한다.
- [ ]  고객에게 배달을 시작 ( `배달중` )할 수 있다.
    - [ ]  배달 시작 시 해당 주문은 반드시 존재하는 주문이어야 한다.
    - [ ]  배달 시작 시 해당 주문의 타입은 반드시 `배달` 이어야 한다.
    - [ ]  배달 시작 시 해당 주문의 상태는 반드시 `진행` 이어야 한다.
    - [ ]  배달 시작 시 해당 주문의 상태를 `배달중`으로 변경해야 한다.
- [ ]  주문의 배달을 완료 할 수 있다.
    - [ ]  `배달완료` 시 해당 주문은 반드시 존재하는 주문이어야 한다.
    - [ ]  `배달완료` 시 해당 주문의 타입은 반드시 `배달` 이어야 한다.
    - [ ]  `배달완료` 시 해당 주문의 상태는 반드시 `배달중` 이어야 한다.
    - [ ]  `배달완료` 시 해당 주문의 상태를 `배달완료`로 변경 해야 한다.
- [ ]  주문을 `완료` 처리 할 수 있다.
    - [ ]  주문 완료 시 해당 해당 주문은 반드시 존재하는 주문이어야 한다.
    - [ ]  주문 완료시 해당 주문의 타입이 배달인 경우 주문의 상태는 반드시 `배달완료` 이어야 한다.
    - [ ]  주문 완료시 해당 주문의 타입이 테이크아웃 이거나 매장내 식사 인 경우 해당 주문의 상태는 반드시 `제공완료` 이어야 한다.
    - [ ]  주문 완료 시 주문의 상태는 `완료` 로 변경 되어야 한다.
    - [ ]  주문 타입이 매장내 식사 인 경우 해당되는 주문 테이블은 사용자 0명 및 비움 처리 되어야 한다.
- [ ]  모든 주문을 조회 할 수 있다.

주문 테이블

- [ ]  주문 테이블은 실제 식당의 테이블 좌석이다.
- [ ]  주문 테이블을 생성 할 수 있다.
    - [ ]  주문 테이블은 각각의 이름, 이용자 수, 테이블 사용 유무로 이루어진다.
    - [ ]  주문 테이블의 이름은 비어있거나 공백 일 수 없다.
    - [ ]  주문 테이블 생성시 기본 값은 인원 수 0, `테이블 사용 않함` 이다.
- [ ]  주문 테이블에 손님이 착석하게 되면 다른 사람은 사용 할 수 없다.
- [ ]  주문 테이블은 손님이 나가게 되면 해당 주문 테이블은 다시 `테이블 사용 가능` 상태가 가 된다.
    - [ ]  해당 주문의 상태는 `완료` 이어야 한다.
    - [ ]  주문 테이블의 이용자수 0, `테이블 사용 안함`으로 변경한다.
- [ ]  주문 테이블은 이용자 수를 변경 할 수 있다.
    - [ ]  실제 존재하는 테이블 이어야 한다.
    - [ ]  이용자 수 변경시 해당 수는 0보다 작을 수 없고 주문 은 테이블 상태가 `테이블 사용 안함` 이어야 한다.
- [ ]  모든 테이블을 조회할 수 있다.


## 용어 사전

| 한글명 | 영문명 | 설명 |
| --- | --- | --- |

## 모델링
