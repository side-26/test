<template lang="">
  <div class="mt-12">
    <div class="flex justify-between items-center">
      <div class="font-bold text-sm text-gray-700">09981561464</div>
      <div>
        <a
          @click="handleChangePhoneNumber()"
          href="#"
          class="text-cyan-500 text-sm font-bold"
          >ویرایش شماره تلفن</a
        >
      </div>
    </div>
    <form @submit="handleArrive">
      <div class="text-gray-500 font-bold my-5">کد تایید</div>
      <div class="flex justify-evenly items-center mb-5">
        <section class="flex justify-between">
          <div class="focus:border-cyan-500 mx-2" v-for="item in 4" :key="item">
            <input
              @keydown="handleMoveInput($event)"
              type="text"
              name=""
              placeholder="-"
              class="w-14 h-12 pr-6 placholder:font-bold border-none outline-cyan-500 rounded-xl"
              ref="4"
            />
          </div>
        </section>
        <div>
          <a href="#" class="font-bold text-cyan-700 text-sm">ارسال مجدد</a>
        </div>
      </div>
      <div class="w-full pb-5">
        <button class="py-3 bg-cyan-500 w-full rounded-xl text-white">ورود</button>
      </div>
    </form>
  </div>
</template>
<script>
import { ref,watch } from "vue";
export default {
  setup(props,{emit}) {
    const input = ref();
    const handleArrive = () => {
      alert("welcome");
    };
    const handleChangePhoneNumber = () => {
      alert("you change route!!1");
      emit('handleChangeStage')
    };
    const handleMoveInput = (evt) => {
      if(evt.target.value.length===0)
        input.value.focus();
    };
    
    return {
      input,
      handleArrive,
      handleChangePhoneNumber,
      handleMoveInput,
    };
  },
};
</script>
<style lang=""></style>
