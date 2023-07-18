# Vue.js Simple Toast Component

## Usage

1. Add the following code to any part of your HTML.
```
<div>
    <toast ref="toast" />
</div>
```

2. Add the following code to your Vue.js methods.
```
methods: {
    showToast: function (e) {
        this.$refs.toast.showSuccess('変更内容を保存しました')
    }
}
```
