<template>
  <div>
    <div id="toast" class="toast">
      <img id="icon" src="check-circle.svg" />
      <p id="text"></p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.toast {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  box-sizing: border-box;
  position: fixed;
  width: 312px;
  height: 60px;
  top: 100px;
  left: 50%;
  right: 50%;
  padding: 12px;
  color: #fff;
  transform: translate(-50%, -500px);
  img {
    width: 24px;
    height: 24px;
    margin-right: 12px;
  }
  &.is-success {
    background-color: #f0f6fa;
    border: 1px solid #a7c3d4;
    border-radius: 4px;
    box-shadow: 0px 2px 12px rgb(0 0 0 / 11%);
    p {
      color: #4b7188;
      font-size: 16px;
      font-weight: bold;
    }
  }
  &.is-error {
    background-color: #fff4f4;
    border: 1px solid #ff9c9c;
    border-radius: 4px;
    box-shadow: 0px 2px 12px rgb(0 0 0 / 11%);
    p {
      color: #eb5858;
      font-size: 16px;
      font-weight: bold;
    }
  }
  &.is-show {
    animation: anime 3s ease 1 normal;
  }
}
@keyframes anime {
  16.666% {
    transform: translate(-50%, 0);
  } // 0.5秒
  83.333% {
    transform: translate(-50%, 0);
  } // 2.5秒
}
</style>

<script>
export default {
  data() {
    return {
      isVisible: false,
    };
  },
  methods: {
    showSuccess: function (message) {
      this.showToast('success', message, 'check-circle.svg');
    },
    showError: function (message) {
      this.showToast('error', message, 'alert-triangle.svg');
    },
    showToast: function (status, message, iconSrc) {
      if (this.isVisible) {
        return false;
      }
      const toast = document.getElementById('toast');
      toast.classList.add('is-' + status);
      toast.classList.add('is-show');

      const icon = document.getElementById('icon');
      icon.src = iconSrc;

      const text = document.getElementById('text');
      text.innerHTML = message;
      this.isVisible = true;
    },
    closeModal() {
      this.show = false;
    },
  },
  mounted() {
    const toast = document.getElementById('toast');
    toast.addEventListener('animationend', () => {
      toast.className = 'toast';

      const icon = document.getElementById('icon');
      icon.src = '';

      const text = document.getElementById('text');
      text.innerHTML = '';
      this.isVisible = false;
    });
  },
};
</script>
