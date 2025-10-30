<script setup lang="ts">
useHead({
  title: 'Contacts',
  meta: [
    { name: 'description', content: 'Contact page'}
  ]
})

const name = ref<string>('');
const email = ref<string>('');
const message = ref<string>('');
const isSub = ref<boolean>(false);
const resultMessage = ref<string>('');

interface ContactsResponse {
  hello: {
    name: string,
    email: string,
    message: string
  }
}

const submitForm = async (e: Event) => {
  isSub.value = true;
  resultMessage.value = '';


    const error = await $fetch<ContactsResponse>('/api/contacts', {
      method: 'POST',
      body: {
        name: name.value,
        email: email.value,
        message: message.value,
      }
    })
  
  


    if(error.hello.name == '') {
      resultMessage.value = 'Error: ' + error;
      console.log(error)
    } else {
      resultMessage.value = 'Success';
      name.value = '';
      email.value = '';
      message.value = '';
      isSub.value = false;
    }

}
</script>

<template>
  <div>
    <h1>Contact</h1>
    <form @submit.prevent="submitForm">
      <input id="name" v-model="name" type="text" class="form-control" placeholder="Enter name"><br>
      <input id="email" v-model="email" type="text" class="form-control" placeholder="Enter email"><br>
      <textarea id="message" v-model="message" name="message" placeholder="Enter message" class="form-control"></textarea><br>
      <button type="submit" class="btn btn-primary" :disabled="isSub">
        {{ isSub ? 'Sending...' : 'Send' }}
      </button>
    </form>

    <p v-if="resultMessage" class="mt-3 alert alert-success"> {{ resultMessage }}</p>
  </div>
</template>

<style scoped></style>
