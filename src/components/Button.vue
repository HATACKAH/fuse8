<template>
    <button>
        <span>See More</span>
        <svg
            width="7"
            height="17"
            viewBox="0 0 7 17"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
        >
            <path
                d="M1 1L5.043 8.41667L1 15.8333"
                stroke="#363636"
                stroke-width="2"
                stroke-linecap="round"
            />
        </svg>
    </button>
</template>

<script>
export default {
    name: 'Button',
};
</script>

<style scoped>
button {
    display: flex;
    align-items: center;
    justify-content: center;

    width: 150px;
    height: 50px;
    border: 1px solid #d8d8d8;
    border-radius: 25px;
    position: relative;
    left: 50%;
    transform: translate(-50%, 0);
    background: white;
    margin-top: 60px;
    cursor: pointer;
    font-weight: bold;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: -0.3px;
}
span {
    margin-right: 5px;
}
</style>
