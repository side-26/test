<template lang="">
  <div>
    <form class="mt-8" @submit.prevent="handleSubmit()">
      <div class="flex flex-col mt-4 pb-5 border-b-2 border-b-gray-300">
        <label for="phone_number"> شماره موبایل* </label>
        <input
          type="text"
          placeholder="شماره تلفن خود را وارد کنید"
          name="phone_number"
          class="border-0 focus:outline-blue-400 my-4 py-2 rounded-xl placeholder:pr-1 pr-3"
        />
      </div>
      <div class="pt-5 text-white">
        <button
          type="submit"
          class="py-2 px-10 w-full bg-cyan-500 font-medium rounded-xl hover:bg-cyan-600"
        >
          ورود به تست
        </button>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  name: "MobileForm",
  setup(props, { emit }) {
    const handleSubmit = () => {
      emit("handleStage");
    };
    return {
      handleSubmit,
    };
  },
};
</script>
<style lang=""></style>
