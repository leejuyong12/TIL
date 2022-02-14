# Vue lifecycle hook

Vue2 에서 Vue3로 넘어오면서 lifecycle hook 명칭이 변화되었습니다.

Vue2 → Vue3

- beforeCreaet → setup()
- created → setup()
- beforeMount → onBeforeMount
- mounted → onMounted
- beforeUpdate → onBeforeUpdate
- updated → onUpdated
- beforeUnmount → onBeforeUnmount
- unmounted → onUnmounted
- errorCaptured → onErrorCaptured
- renderTracked → onRenderTracked
- renderTriggerd → onRenderTriggered



- `onBeforeMount` -장착이 시작되기 전에 호출됩니다.
- `onMounted` -컴포넌트가 마운트 될 때 호출됩니다.
- `onBeforeUpdate` -반응 형 데이터가 변경 될 때와 다시 렌더링하기 전에 호출됩니다.
- `onUpdated` -다시 렌더링 후 호출
- `onBeforeUnmount` -Vue 인스턴스가 파괴되기 전에 호출됩니다.
- `onUnmounted` -인스턴스가 파괴 된 후 호출됩니다.
- `onActivated` -연결 유지 구성 요소가 활성화되면 호출됩니다.
- `onDeactivated` -연결 유지 구성 요소가 비활성화 될 때 호출됩니다.
- `onErrorCaptured` -하위 구성 요소에서 오류가 캡처 될 때 호출됩니다.



- create - 구성 요소의 생성에서 실행됩니다.
- mount - DOM이 마운트될 때 실행됩니다.
- update - 반응형 데이터가 수정될 때 실행됩니다.
- destroy - component가 파괴되기 직전에 실행됩니다.
