<template>
    <DetailResourceBase :endpoint="$router.currentRoute.params.endpoint" />
</template>

<script>
    import DetailResourceBase from "./DetailResourceBase";
    export default {
        name: "DetailBase",
        components: {DetailResourceBase}
    };
</script>

<style lang="scss" scoped></style>