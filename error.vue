<template>
    <NuxtLayout>
        <div class="flex flex-col">
        <div v-if="error.statusCode === 404" class="prose">
            <h1>404</h1>
            <p>I guess page doesn't exist.</p>
        </div>
        <div v-else class="prose">
            <h1>Dang</h1>
            <p>It looks like something broke.</p>
            <p>Sorry about that.</p>
        </div>
        <div class="prose">
            <p><strong>{{ error.message }}</strong></p>
            <p>
                Go to the
                <a
                class="hover:cursor-pointer"
                @click="handleError">
                Back to Home Page
            </a>
            </p>
        </div>
    </div>
    </NuxtLayout>
</template>
<script setup>
    const error = useError();
    const handleError = () => {
        clearError({
            redirect: '/'
        });
    };
</script>
