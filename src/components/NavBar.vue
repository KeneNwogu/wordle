<template>
    <ul>
        <li><img src="../assets/icons8-help-24.png" alt="" srcset=""></li>
        <li class="title"><h2>WORDLE</h2></li>
        <div>
            <li style="margin-right: 12px"><img src="../assets/icons8-settings-50.png" alt="" srcset=""></li>
            <li><img src="../assets/icons8-stats-32.png" alt="" srcset=""></li>
        </div>
    </ul>
</template>

<style>
    ul{
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: absolute;
        top: 0;
        left: 0;
        padding: 0;
        /* right: 0; */
        width: 100%;
        list-style: none;
        border-bottom: 0.1em solid grey;
    }
   
    ul > li{
        padding: 5px;
        flex: 1;
        display: flex;
        justify-content: center;
    }

    ul > li:first-child > img{
        margin-right: auto;
    }
    
    ul > div{
        display: flex;
        justify-content: flex-end;
        flex: 1;
        margin-left: auto;
    }
    li.title{
        text-transform: uppercase;
        font-weight: 800;
    }
    img{
        width: 24px;
        height: 24px;
    }
</style>

<script>
export default {
    name: "NavBar",
    data(){
        return {

        }
    }
}
</script>