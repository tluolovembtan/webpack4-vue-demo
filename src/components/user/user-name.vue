<style>
</style>

<template>
    <div >
            <div class="form-group">
                <label  class="col-sm-2 control-label">用户名:</label>
                <div class="col-sm-10">
                    <input type="text" class="form-control" v-on:change="userNameChange" v-model="username" :placeholder="placeholder">

                </div>
            </div>
        <div class="form-group">
            <label   class="col-sm-2 control-label">测试:</label>
            <div class="col-sm-10">
                <shenyi-text></shenyi-text>

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        mounted(){

        },
        props:['placeholder'],
        data: function () {
            return {
                username:"",
                showErrorLabel: false
            }
        },
        methods:{
            showLabel(){
                if(this.checkUserName(this.username)){
                    this.showErrorLabel=false;
                } else {
                    this.showErrorLabel=true;
                }

            },
            userNameChange(){
                this.$store.state.users.user_name = this.username;
                //this.$emit("childChange","username",this.username);

            }
        }
    }
</script>