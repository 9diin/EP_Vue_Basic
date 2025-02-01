<template>
    <!-- HTML (템플릿) 영역 -->
    <h1>{{ count }}</h1>
    <h2>Vue.js 라이프사이클 테스트</h2>
    <button @click="incrementCount">카운트 증가</button>
</template>

<script>
/** 스크립트 영역 */
export default {
    data() {
        return {
            count: 10,
        };
    },
    /** 라이프사이클 훅(Hooks) */
    /** 생성단계(Creation) */
    beforeCreate() {
        console.log("라이프사이클 훅 - beforeCreate: 인스턴스가 생성되기 전", this.count);
    },
    created() {
        console.log("라이프사이클 훅 - created: 인스턴스가 생성되기 후", this.count);
    },

    /** 마운트 단계(Mounting) */
    beforeMount() {
        // DOM에 렌더링 되기 직전
        console.log("라이프사이클 훅 - beforeMount: DOM에 렌더링 되기 직전", document.querySelector("h2"));
    },
    mounted() {
        // DOM에 렌더링 된 후
        console.log("라이프사이클 훅 - mounted: DOM에 렌더링 된 후", document.querySelector("h2")); // 최상위 DOM 요소
    },

    /** 업데이트 단계(Updating) */
    beforeUpdate() {
        console.log("라이프사이클 훅 - beforeUpdate: DOM이 업데이트 되기 전", this.count);
        console.log("라이프사이클 훅 - beforeUpdate: DOM에 렌더링 되기 전", document.querySelector("h1").textContent);
    },
    updated() {
        console.log("라이프사이클 훅 - updated: DOM이 업데이트 되기 후", this.count);
        console.log("라이프사이클 훅 - updated: DOM에 렌더링 되기 후", document.querySelector("h1").textContent);
    },

    methods: {
        incrementCount() {
            this.count++; // 카운트 값을 증가
        },
    },
};
</script>

<style scoped>
/** 스타일 영역 */
/** scoped: 해당 컴포넌트에서만 style 태그에 입력된 CSS 효과가 적용된다는 의미 */
</style>
