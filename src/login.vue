<template>
    <div class="container-ful">
        <div class="flexbox-frm">
            <div class="container-frm">
                <div class="container-grid">
                    <div class="container-img"></div>
                    <div class="container-login">
                        <div class="box-login">
                            <img class="img-login" src="./img/img_337531.png" alt="" srcset="">
                            <h1>Sign in</h1>
                            <div class="container-fromlog">
                                <input type="text" placeholder="Username">
                            </div>
                            <div class="container-fromlog">
                                <input type="password" placeholder="password">
                            </div>
                            <div class="container-fromlog">
                                <button @click="login" >Sign In</button>
                            </div>
                            <div class="container-forgot">
                                <div class="text-forgot">
                                    <p>Forgot password?</p>
                                </div>
                                <div class="text-signup">
                                    <p>Sign up</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    methods: {
        async login() {
            alert("login!")
            let result = await axios.get("http://localhost:8000/getdata/?username=dpkeaw")
            console.log(result)
        }
    },
}
</script>

<style>
.container-ful {
    background: #0F2027;
    background: -webkit-linear-gradient(to top, #2C5364, #203A43, #0F2027);
    background: linear-gradient(to top, #2C5364, #203A43, #0F2027);
    width: 100%;
    height: 100vh;
}

.container-frm {
    width: 900px;
    height: auto;
    box-shadow: 8px 8px 10px #00000036;
}

.flexbox-frm {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100vh;
}

.container-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    height: 100%;
}

.container-img {
    background-image: url("./img/loginbg1.jpg");
    background-size: cover;
    background-position: center;
}

.container-login {
    background-color: rgb(255, 255, 255);
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
}

input[type="text"],
input[type="password"] {
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 10px;
    width: 100%;
    outline: none;
    transition: 0.5s;
}
input[type="text"]:hover,
input[type="password"]:hover {
    border: 1px solid #1f4d61;
    box-shadow: 1px 1px 10px #2C5364;
}

.box-login {
    width: 100%;
    margin: 30px;
    padding: 50px;
}

.container-fromlog {
    display: flex;
    padding: 10px;
}

button {
    width: 100%;
    padding: 12px;
    border: none;
    border-radius: 5px;
    text-transform: uppercase;
    outline: none;
    cursor: pointer;
    background: #0F2027;
    color: #fff;
    transition: 0.5s;
}
button:hover {
    background: #1f3d49;
    box-shadow: 1px 1px 10px #2C5364;
}

h1 {
    color: #0F2027;
    margin: 0;
    padding: 10px;
    text-transform: uppercase;
    font-size: clamp(20px, 2vw, 30px);
}

.img-login {
    width: 30%;
}

.container-forgot {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    padding: 0 10px;
    margin: 0;
}

.text-forgot {
    text-align: start;
    color: #0F2027;
    cursor: pointer;
    transition: 0.5s;
    font-size: clamp(12px, 1vw, 16px);
}
.text-forgot:hover {
    color: #ff0000;
}

.text-signup {
    text-align: end;
    color: #0F2027;
    cursor: pointer;
    transition: 0.5s;
    font-size: clamp(12px, 1vw, 16px);
}
.text-signup:hover {
    color: #87b0c4;
}

@media only screen and (max-width: 1000px) {
    .container-frm {
        width: 80vw;
        height: 60%;
    }

    .box-login {
        width: 100%;
        margin: 10px;
        padding: 10px;
    }
}

@media only screen and (max-width: 600px) {
    .container-frm {
        width: 90vw;
        height: 60%;
    }

    .box-login {
        width: 100%;
        margin: 10px;
        padding: 10px;
    }

    .container-img {
        background-image: none;
    }

    .container-grid {
        display: grid;
        grid-template-columns: 1fr;
        height: 100%;
    }
}
</style>