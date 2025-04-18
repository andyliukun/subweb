<template>
  <html lang="en" class="dialog-overlay" dir="ltr">
    <div class="dialog" style="overflow-y: auto">
      <div
        aria-labelledby="swal2-title"
        aria-describedby="swal2-html-container"
        class="swal2-popup swal2-modal swal2-icon-success swal2-show"
        tabindex="-1"
        role="dialog"
        aria-live="assertive"
        aria-modal="true"
        style="display: grid"
      >
        <component :is="$store.state.app.dialog.icon" />
        <!-- icon -->
        <h2 class="swal2-title" style="display: block">
          {{ $store.state.app.dialog.title }}
        </h2>
        <!-- title -->
        <div class="swal2-html-container" style="display: block">
          {{ $store.state.app.dialog.message }}
        </div>
        <!-- message -->
        <div class="swal2-actions" style="display: flex">
          <component :is="$store.state.app.dialog.button" />
        </div>
        <!-- button -->
      </div>
    </div>
  </html>
</template>

<script>
import IconSuccess from './icon/success.vue';
import IconInfo from './icon/info.vue';
import IconWarning from './icon/warning.vue';
import IconError from './icon/error.vue';
import ButtonDefault from './button/ButtonDefault.vue';
import ButtonSuccess from './button/ButtonSuccess.vue';
import ButtonWarning from './button/ButtonWarning.vue';
import ButtonError from './button/ButtonError.vue';
import ButtonConfirmDefault from './button/ConfirmDefault.vue';
import ButtonConfirmSuccess from './button/ConfirmSuccess.vue';
import ButtonConfirmWarning from './button/ConfirmWarning.vue';
import ButtonConfirmError from './button/ConfirmError.vue';
export default {
  name: 'DialogView',
  components: {
    ButtonConfirmDefault,
    ButtonConfirmSuccess,
    ButtonConfirmWarning,
    ButtonConfirmError,
    ButtonDefault,
    ButtonSuccess,
    ButtonWarning,
    ButtonError,
    IconSuccess,
    IconInfo,
    IconWarning,
    IconError,
  },
};
</script>

<style scoped>
/* 当前 div 样式加上 z-index: 999999 用于覆盖其他组件 */
.dialog-custom {
  z-index: 999999;
}

.dialog-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.dialog {
  background: #fff;
  border-radius: 8px;
  width: 300px;
  padding: 20px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
</style>
