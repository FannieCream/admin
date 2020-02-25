<template>
    <div class="image">
    <div class="login">
        <h1>青马班PC管理端登录</h1>
        <form>
            <table class="login-table">
                <tr>
                    <td>账号</td>
                    <td><input type="text" name="username" required="required"></td>
                </tr>
                <tr>
                    <td>密码</td>
                    <td><input type="password" name="password" required="required"></td>
                </tr>
                <tr>
                    <td>验证码</td>
                    <td><input type="text" name="terminal" required="required"></td>
<!--                    <td><canvas id="code" onclick="change()"></canvas></td>-->
                </tr>
            </table>
            <div id="code">
                <canvas id="code-image"></canvas>
                <button class="btn-primary" id="code-btn">重置</button>
            </div>

            <button type="button" class="btn btn-success" style="margin-left: 180px"><router-link to="/home">确认</router-link></button>
        </form>
    </div>
    </div>
</template>

<script>
    export default {
        name: "login",
        // data(){
        //     return {
        //         image: {
        //             backgroundImage: "url(" + require("../assets/bgbook2.png") + ")",
        //             backgroundRepeat: "no-repeat",
        //             backgroundSize: "cover"
        //         }
        //
        //     }
        // },
        methods:{
        //     //验证二维码实现
        //     change: function()  {
        //         var show_num = [];
        //         draw(show_num);
        //     },
        //
        //     draw(show_num){
        //         var canvas_width = document.getElementById('code-image').clientWidth;
        //         var canvas_height = document.getElementById('code-image').clientHeight;
        //         var canvas = document.getElementById('code-image');
        //         var context = canvas.getContext("2d");
        //         canvas.width = canvas_width;
        //         canvas.height = canvas_height;
        //         var sCode = "A,B,C,E,F,G,H,J,K,L,M,N,P,Q,R,S,T,W,X,Y,Z,1,2,3,4,5,6,7,8,9,0,q,w,e,r,t,y,u,i,o,p,a,s,d,f,g,h,j,k,l,z,x,c,v,b,n,m";
        //         var aCode = sCode.split(",");
        //         var aLength = aCode.length;//获取到数组的长度
        //
        //         for(var i=0; i<=3; i++){
        //             var j = Math.floor(Math.random() * aLength);//获取到随机的索引值
        //             var deg = Math.random() * 30 * Math.PI / 180;//产生0~30之间的随机弧度
        //             var txt = aCode[j];//得到随机的一个内容
        //             show_num[i] = txt;
        //             var x = 10 + i * 20;//文字在canvas上的x坐标
        //             var y = 20 + Math.random() * 8;//文字在canvas上的y坐标
        //             context.font = "bold 23px 微软雅黑";
        //
        //             context.translate(x, y);
        //             context.rotate(deg);
        //
        //             context.fillStyle = randomColor();
        //             context.fillText(txt, 0, 0);
        //
        //             context.rotate(-deg);
        //             context.translate(-x, -y);
        //         }
        //         for (var i = 0; i <= 5; i++) { //验证码上显示线条
        //             context.strokeStyle = randomColor();
        //             context.beginPath();
        //             context.moveTo(Math.random() * canvas_width, Math.random() * canvas_height);
        //             context.lineTo(Math.random() * canvas_width, Math.random() * canvas_height);
        //             context.stroke();
        //         }
        //         for (var i = 0; i <= 30; i++) { //验证码上显示小点
        //             context.strokeStyle = randomColor();
        //             context.beginPath();
        //             var x = Math.random() * canvas_width;
        //             var y = Math.random() * canvas_height;
        //             context.moveTo(x, y);
        //             context.lineTo(x + 1, y + 1);
        //             context.stroke();
        //         }
        //     },
        //
        //     randomColor(){//得到随机的颜色值
        //         var r = Math.floor(Math.random() * 256);
        //         var g = Math.floor(Math.random() * 256);
        //         var b = Math.floor(Math.random() * 256);
        //         return "rgb(" + r + "," + g + "," + b + ")";
        //     }
         }
    }

</script>

<style lang="less" scoped>
    /*body {*/
    /*    !*background-color: #9BCD9B;*!*/
    /*    background: url(../assets/bgbook2.png) no-repeat center center;*/
    /*    background-size: cover;*/
    /*}*/
    .image {
        position: fixed;
        background: url("../assets/bgbook2.png") no-repeat center center;
        background-size: cover;
        width: 100%;
        z-index: -99;
    }

    .login {
        background-color: white;
        width: 400px;
        height: 450px;
        border:2px solid green;
        margin: 0 auto;
        border-radius: 20px;
        position: relative;
        margin-top: 65px;
        margin-bottom: 80px;
        // 添加阴影
        -webkit-box-shadow: #666 0px 0px 20px;
        -moz-box-shadow: #666 0px 0px 20px;
        box-shadow: #666 0px 0px 20px;

        h1 {
            margin-top: 50px;
            color: white;
            font-size: 20px;
            font-weight: bolder;
            letter-spacing: 2px;
            text-shadow: 1px 1px 0 darkgreen,1px -1px 0 darkgreen,-1px -1px 0 darkgreen,-2px 2px 0 darkgreen;
            text-align: center;
        }
        p {
            text-align: center;
        }
    }
    .login:hover {
        -webkit-box-shadow: #bbb 0px 0px 60px;
        -moz-box-shadow: #bbb 0px 0px 60px;
        box-shadow: #bbb 0px 0px 60px;
    }
    .login-table {
        text-align: center;
        margin:auto;
        margin-top: 50px;
        tr {
            margin-bottom: 30px;
            height: 50px;
            /*border: 1px solid black;*/
            color: #2b542c;
            font-weight: bolder;

            td{
                padding: 0 5px;
            }
        }
    }
    input[type=text], input[type=password]{
        width: 180px;
        height: 30px;
        border-radius: 4px;
        box-sizing: border-box;
    }
    .btn-submit {
        background-color: green ;
        color: white;
    }
    a {
        color: white;
    }
    #code {
        /*margin: 0 auto;*/
        margin-top: 5px;
        margin-left: 132px;
        text-align: center;
        width: 180px;
        height: 60px;
        /*border: 2px solid red;*/

        #code-image {
            border: 1px solid #ccc;
            width: 120px;
            height:40px;
            float: left;
        }
        #code-btn {
            margin-top: 10px;
            float: right;
            /*border: 2px solid black;*/
        }
    }
</style>

