# Transfer Integration

## Overview

트랜스퍼 연동하기 위한 방법을 정의 합니다.

## Usage

럭키모나코가 제공하는 api를 호출하여 사용자를 생성하고 지갑을 생성하고 금액을 조정할 수 있습니다. 
!! 럭키모나코와 해당 구조를 사용하기로 합의되어야만 사용 가능합니다.

## APIs

* /user/create - 유저를 생성합니다.
* /user/create_wallet - 특정 재화의 지갑을 생성합니다.
* /user/info - 유저의 정보를 조회합니다. (모든 지갑의 정보도 조회 됩니다.)
* /user/balance - 유저의 특정 재화 보유량을 확인합니다.
* /user/charge - 유저에게 특정 재화를 지급합니다.
* /user/refund - 유저에게 특정 재화를 돌려받습니다.
* /log/get - 게임 로그를 얻어옵니다.   