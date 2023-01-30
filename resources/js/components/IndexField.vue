<template>
    <div class="w-full permissions-overflow-auto permissions-inline-block">
        <div v-for="(permissions, group) in field.options" :key="group" class="permissions-inline-flex">
            <div class="permissions-px-1">
                <h3 class="permissions-text-[0.65rem] permissions-leading-[0] permissions-mt-1">
                    {{ __(group) }}</h3>
                <div
                    v-for="permission in permissions"
                    :key="permission.option"
                    class="permissions-inline-block permissions-leading-[0]"
                >
                    <span
                        :class="(field.value ? field.value.includes(permission.option) : false) ? 'permissions-bg-green-400' : 'permissions-bg-red-500'"
                        class="permissions-inline-block permissions-rounded-full permissions-w-1 permissions-h-1 permissions-text-xs permissions-mr-0.5"
                    />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['resourceName', 'field'],
}
</script>
