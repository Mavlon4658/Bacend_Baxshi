<template>
  <div class="pa-5">
    <div>
      <h2>Biz haqimizda ma'lumot qo'shing</h2>
      <form action="" class="py-5">
        <div class="pt-5">
            <div class="label pb-3">
                San'atni chuqurroq o'rganish haqida qisqacha matn kiriting.
            </div>
          <v-textarea
            solo
            name="input-7-4"
            label="Matn kiriting"
            v-model="textarea"
            :rules="Textarea"
          ></v-textarea>
        </div>
      </form>
    </div>
    <div></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      textarea: '',

      Textarea: [
        (v) => !!v || 'Matnni kiritish majburiy.',
        (v) => v.length <= 200 || 'Name must be less than 10 characters',
      ],
    }
  },
}
</script>

<style scoped>
</style>
