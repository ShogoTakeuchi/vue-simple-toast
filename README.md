# Vue.js Simple Toast Component

<img width="400" src="https://github.com/ShogoTakeuchi/vue-simple-toast/assets/56812464/3e130d3e-40c3-431c-9db6-678c7d59ce47">
<br>
<img width="400" src="https://github.com/ShogoTakeuchi/vue-simple-toast/assets/56812464/fc01c8b1-7047-4597-af5d-5e441d4952e6">

## Usage

1. Add the following code to any part of your HTML.
```
<div>
    <toast ref="toast" />
</div>
```

2. Add the following code to your Vue component methods.
```
methods: {
    showSuccess: function () {
        this.$refs.toast.showSuccess('Success!!')
    }
    showError: function () {
        this.$refs.toast.showError('Error!!')
    }
}
```
