<template>
    <div class="header">
        <nav>
            <img src="../../img/member.png">
            <router-link tag="li" to="/home">Home</router-link>
            <router-link tag="li" to="/about">About</router-link>
            <router-link tag="li" to="/work">Work</router-link>
        </nav>
    </div>
</template>

<style lang="scss">
    .header {
        width: 100vw;
        height: 30%;
        // padding: 0 10%;
        background: #f7efef;
        margin-bottom: 30px;

        nav {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-around;
            padding: 20px 0;

            img {
                width: 100px;
            }

            li {
                display: inline-block;
                list-style: none;
                margin: 10px 30px;
                text-decoration: none;
                color: #3f51b5;
                font-weight: 900;
                cursor: pointer;

                &:hover {
                    font-style: italic;
                    color: dimgrey;
                }
            }
        }
    }
</style>
