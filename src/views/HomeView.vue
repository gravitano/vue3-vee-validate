<script setup lang="ts">
import { Form } from 'vee-validate';
import TextField from '@/components/forms/TextField.vue';
import { object, string } from 'yup';

const schema = object({
  name: string().required(),
});

const onSubmit = (values: Record<string, any>) => {
  console.log(values);
};
</script>

<template>
  <main>
    <Form @submit="onSubmit" :validation-schema="schema">
      <TextField label="Name" name="name" placeholder="Name" />
      <TextField label="Email" name="email" placeholder="Email" />
      <TextField label="Password" name="password" type="password" />

      <button>Submit</button>
    </Form>
  </main>
</template>
