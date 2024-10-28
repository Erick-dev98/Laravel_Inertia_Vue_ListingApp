<script setup>
import { useForm } from '@inertiajs/vue3';
import Container from '../../Components/Container.vue';
import Title from '../../Components/Title.vue';
import InputField from '../../Components/InputField.vue';
import TextArea from '../../Components/TextArea.vue';
import PrimaryButton from '../../Components/PrimaryButton.vue';

const form = useForm({
    title: null,
    desc: null,
    tags: null,
    email: null,
    link: null,
    image: null,
})

</script>

<template>
    <Head title="- New Listing" />

    <Container>
        <div>
            <Title>Create a new Listing</Title>
        </div>

        <form class="grid grid-cols-2 gap-6">
            <div class="space-y-6">
                <InputField 
                label="Title"
                icon="heading"
                placeholder="My new listing"
                v-model="form.title"
                />

                <InputField 
                label="Tags (separate with comma)"
                icon="tags"
                placeholder="one, two, three"
                v-model="form.tags"
                />

                <TextArea 
                label="Description"
                icon="newspaper"
                placeholder="This is my listing description"
                v-model="form.desc"
                />
            </div>

            <div class="space-y-6">
                <InputField 
                label="Email"
                icon="at"
                placeholder="example@email.com"
                v-model="form.email"
                />

                <InputField 
                label="External Link"
                icon="up-right-from-square"
                placeholder="https://example.com"
                v-model="form.link"
                />                
            </div>

            <div>
                <PrimaryButton>Create</PrimaryButton>
            </div>
        </form>
    </Container>
</template>