<template>
    <div class="login">
        <table class="login-table">
            <caption>青马班PC管理端登录</caption>
            <tr>
                <td>账号</td>
                <td><input type="text" name="username" required="required" ></td>
            </tr>
            <tr>
                <td>密码</td>
                <td><input type="password" name="password" required="required"></td>
            </tr>
            <tr>
                <td>验证码</td>
                <td><input type="text" name="terminal" required="required" ></td>
                <td><button type="submit">重置</button></td>
            </tr>

        </table>
        <button type="submit"><router-link to="/home">确认</router-link></button>

    </div>
</template>

<style lang="less">
    .login-table {
        text-align: center;
        margin:auto;
    }



</style>

