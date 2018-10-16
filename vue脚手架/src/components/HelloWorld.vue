<template>
  <div  class="tab-content hello">   
    <div class="form content1 tab-pane fade in active" id="home" @click="checkForm1" action="https://vuejs.org/"  method="post" novalidate="true">
            <div class="form-group">
                <select class="form-control">
                    <option selected="selected" placeholder="高校">华南师范大学</option>
                    <option>广州大学</option>
                    <option>中山大学</option>
                </select>
            </div>
            <div class="form-group">
                <input type="text"  placeholder="学/工号" class="form-control" id="number" v-model="number" name="number"/>
            </div>
            <div class="form-group">
                <input type="password"  placeholder="密码" class="form-control" id="password1" v-model="password1" name="password1"/>
            </div>
            <a href="javascript:;" class="col-xs-4 col-xs-offset-8 forget">忘记密码？</a>
            <input type="submit"alue="登录" class="btn btn-primary btn-block" data-toggle="modal" data-target="#check">
            <a href="jacascript:'" class="id">使用统一身份认证登录</a>

            <div class="container copy1">
                <div class="footer text-center">
                Copyright &copy;华南师范大学|Fx工作室 All right reserved 
                </div>
            </div>
    </div>

    <div class="form content2 tab-pane fade" id="ios"  @click="checkForm2" action="https://vuejs.org/" method="post" novalidate="true">
            <div class="form-group">
                <input type="email" class="form-control" placeholder="注册邮箱" id="email" v-model="email" name="email">
            </div>
            <div class="form-group">
                <input type="password"  placeholder="密码" class="form-control" id="password2" v-model="password2" name="password2"/>
            </div>
            <a href="javascript:;" class="col-xs-4 col-xs-offset-8 forget">忘记密码？</a>
            <input type="submit"alue="登录" class="btn btn-primary btn-block" data-toggle="modal" data-target="#check">

            <div class="container copy2">
                <div class="footer text-center">
            Copyright &copy;华南师范大学|Fx工作室 All right reserved 
                </div>
            </div>
    </div>

    <!--模态框-->
        <div rol="dialog" class="modal fade col-lg-6 col-lg-offset-4 col-md-7 col-md-offset-2 col-sm-10 col-sm-offset-1" id="check">
            <div class="modal-dialog ">
                <div class="modal-content  " v-if="errors.length">
                    <div class="modal-body">
                        <h3 class="title text-center">登录失败</h3>
                        <p class="content text-center" v-for="error in errors">{{error}}</p>
                    </div>
                    <div class="modal-footer">
                    <a href="#" data-dismiss="modal">关闭</a>
                    </div>
                 </div>
            </div>
        </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      errors: [],
      number:null,
      name: null,
      email: null,
      movie: null,
      password1:null,
      password2:null
    }
  },

  methods:{
     checkForm1(e) {
        this.errors = [];

        if (!this.number||!this.password1) {
            this.errors.push('账号密码不能为空');
        }
        else
        {
            this.errors.push('账号或密码错误');
        }
      },

    checkForm2(e) {
        this.errors = [];
        if (!this.email||!this.password2) {
           this.errors.push('邮箱密码不能为空');
        } 
        else if (!this.validEmail(this.email)&&!this.password2) {
            this.errors.push('请填写正确邮箱');
              }
        else if(!this.validEmail(this.email)&&this.password2){
            this.errors.push('请填写正确邮箱');
              }
        else{
            this.errors.push('邮箱或者密码错误');
              }
        },

    validEmail: function (email) {
              var re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
              return re.test(email);
            }
  }
}
</script>


<style scoped>
.form-control{padding: 0; width:23.6rem; height: 3rem; margin:1.9rem auto 0; border-radius: 0.5rem; border: 0.05rem solid #999; box-shadow:0.2rem 0.2rem 0.3rem #e6e6e6;
              font-size: 1.4rem; color: #333; padding-left: 1.3rem;}
.form-group {margin-bottom: 0;}
.form input::-webkit-input-placeholder { /* WebKit browsers */color:#b5b5b5;}     
.form input:-moz-placeholder { /* Mozilla Firefox 4 to 18 */color:#b5b5b5;}  
.form input::-moz-placeholder { /* Mozilla Firefox 19+ */color:#b5b5b5;}
.form input:-ms-input-placeholder { /* Internet Explorer 10+ */color:#b5b5b5;}

.tab .content1 .forget{color:#ea8542; font-size:1.3rem; margin-top: 1.3rem; padding: 0; }    
.tab .content1 .btn{width: 21.1rem; height: 4rem; margin: 4.3rem auto 0; border-radius: 0.5rem; box-shadow: 0.3rem 0.3rem 0.4rem #e6e6e6; background-color:#ea8542; 
                    border: 0; color: #fff; font-size:1.8rem;}
.tab .content1 .btn:focus{background:#df6b20; color:#fad4c1; }
.tab .content1 .id{display: table; margin:2rem auto; font-size:1.4rem; color:#2a488a;text-decoration:underline;letter-spacing:0.025rem;}

.tab .content2 .forget{color:#ea8542; font-size:1.3rem; margin-top: 1.3rem; padding: 0; } 
.tab .content2 .btn{width: 21.1rem; height: 4rem; margin: 4.7rem auto 0; border-radius: 0.5rem; box-shadow: 0.3rem 0.3rem 0.4rem #e6e6e6; background-color:#18c869; 
                    border: 0; color: #fff; font-size:1.8rem;}
.tab .content2 .btn:focus{background:#05ae53; color:#c9fde1; }

.modal-dialog{margin: 0;}
.modal-content{width: 31.1rem; margin-left: auto; margin-right: auto;margin-top: 18.4rem; border-radius:0.75rem;background: #fff;
                }
.modal-body{padding: 0;}
.modal .title{margin: 0; margin-top: 2rem; font-size:1.9rem; color: #333;}
.modal .content{margin-top:2.5rem; font-size:1.5rem; color:#999; margin-bottom:0; margin-bottom:2.5rem; }
.modal-footer{border-top:0.1rem solid #ebebeb; padding: 0;}
.modal-footer a{display: table; margin:1.3rem auto 1.3rem; color:#ea8542; font-size:1.7rem;}

.copy1 .footer{ font-size:0.5rem;margin-top: 6.5rem;}
.copy2 .footer{ font-size:0.5rem;margin-top: 17rem;}
</style>
