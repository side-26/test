<template lang="">
  <div class="flex justify-center items-center min-h-[100vh]">
    <section class="w-[22%]">
      <figure class="flex justify-center mb-12">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          aria-hidden="true"
          role="img"
          class="iconify iconify--logos h-24 w-20"
          width="37.07"
          height="36"
          preserveAspectRatio="xMidYMid meet"
          viewBox="0 0 256 198"
        >
          <path
            fill="#41B883"
            d="M204.8 0H256L128 220.8L0 0h97.92L128 51.2L157.44 0h47.36Z"
          ></path>
          <path
            fill="#41B883"
            d="m0 0l128 220.8L256 0h-51.2L128 132.48L50.56 0H0Z"
          ></path>
          <path
            fill="#35495E"
            d="M50.56 0L128 133.12L204.8 0h-47.36L128 51.2L97.92 0H50.56Z"
          ></path>
        </svg>
      </figure>
      <div class="font-bold text-2xl pb-5">ورود به تست</div>
      <div class="mt-5 border-b-2 border-b-gray-300">
        <transitionGroup name="list">
          <MessageForm v-if="isEnterd" @handleChangeStage="handleStages" />
          <MobileForm v-else @handleChangeStage="handleStages" />
        </transitionGroup>
      </div>
    </section>
  </div>
</template>
<script>
import MessageForm from "../../components/auth/messageForm/MessageForm.vue";
import MobileForm from "../../components/auth/mobileForm/MobileForm.vue";
import { ref } from "vue";
export default {
  name: "LoginPage",
  components: {
    MessageForm,
    MobileForm,
  },
  setup(props) {
    const isEnterd = ref(false);
    const handleStages = (nextStage) => {
      isEnterd.value = !isEnterd.value;
      console.log(stage.value);
    };
    return {
      isEnterd,
      handleStages,
    };
  },
};
</script>
<style lang="css">
.list-move, /* apply transition to moving elements */
.list-enter-active,
.list-leave-active {
  transition: all 0.5s ease;
}

.list-enter-from,
.list-leave-to {
  opacity: 0;
  transform: translateX(30px);
}

/* ensure leaving items are taken out of layout flow so that moving
   animations can be calculated correctly. */
.list-leave-active {
  position: absolute;
}
</style>
