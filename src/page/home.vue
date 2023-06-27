<script>
export default {
    data(){
        return {
            len : 15,
            Result : '',
            arrTxtCaps : ['A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'],
            arrTxt : ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'],
            numer : ['1','2','3','4','5','6','7','8','9','0'],
            mark : ['(',')','[',']','{','}','&','^','%','$','#','@','!','~','|','/','?','>','<','-','_','*',';',',',':'],
            symbol : false ,
            num : true ,
            char : true ,
            charCaps : false ,
            CCCNS : ['(',')','[',']','{','}','&','^','%','$','#','@','!','~','|','/','?','>','<','-','_','*',';',',',':','a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z','1','2','3','4','5','6','7','8','9','0'],
            SNC : ['(',')','[',']','{','}','&','^','%','$','#','@','!','~','|','/','?','>','<','-','_','*',';',',',':','1','2','3','4','5','6','7','8','9','0','a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'],
            SCCC : ['(',')','[',']','{','}','&','^','%','$','#','@','!','~','|','/','?','>','<','-','_','*',';',',',':','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z','a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'],
            SNCC : ['(',')','[',']','{','}','&','^','%','$','#','@','!','~','|','/','?','>','<','-','_','*',';',',',':','1','2','3','4','5','6','7','8','9','0','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'],
            NCCC : ['1','2','3','4','5','6','7','8','9','0','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z','a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'],
            SN : ['(',')','[',']','{','}','&','^','%','$','#','@','!','~','|','/','?','>','<','-','_','*',';',',',':','1','2','3','4','5','6','7','8','9','0'],
            SCC : ['(',')','[',']','{','}','&','^','%','$','#','@','!','~','|','/','?','>','<','-','_','*',';',',',':','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'],
            SC : ['(',')','[',']','{','}','&','^','%','$','#','@','!','~','|','/','?','>','<','-','_','*',';',',',':','a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'],
            NC : ['1','2','3','4','5','6','7','8','9','0','a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'],
            NCC : ['1','2','3','4','5','6','7','8','9','0','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'],
            CCC : ['A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z','a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'],
        }
    },
    methods : {
        builder (){
            if (this.symbol && this.num && this.char && this.charCaps){ // کاراکتر و عدد و حرف و حرف بزرگ
                this.Result = this.cTest(this.CCCNS)
            }else if (this.symbol && this.num && this.charCaps){// کاراکتر و عدد و حرف بزرگ
                this.Result = this.cTest(this.SNCC)
            }else if (this.symbol && this.num && this.char){// کاراکتر و عدد و حرف  
                this.Result = this.cTest(this.SNC)
            }else if (this.symbol && this.charCaps && this.char){//  کاراکتر حرف و حرف بزرگ
                this.Result = this.cTest(this.SCCC)
            }else if (this.num && this.charCaps && this.char){//  عدد و حرف و حرف بزرگ
                this.Result = this.cTest(this.NCCC)
            }else if (this.symbol && this.num){// کاراکتر و عدد
                this.Result = this.cTest(this.SN)
            }else if (this.symbol && this.charCaps){// کاراکتر و حرف بزرگ
                this.Result = this.cTest(this.SCC)
            }else if (this.symbol && this.char){// کاراکتر و حرف
                this.Result = this.cTest(this.SC)
            }else if (this.num && this.char){// عدد و حرف
                this.Result = this.cTest(this.NC)
            }else if (this.num && this.charCaps){// عدد و حرف بزرگ
                this.Result = this.cTest(this.NCC)
            }else if (this.char && this.charCaps){// حرف و حرف بزرگ 
                this.Result = this.cTest(this.CCC)
            }else if (this.symbol){// کاراکتر
                this.Result = this.cTest(this.mark)
            }else if (this.num){// عدد
                this.Result = this.cTest(this.numer)
            }else if (this.char){// حرف
                this.Result = this.cTest(this.arrTxt)
            }else if (this.charCaps){// حرف بزرگ
                this.Result = this.cTest(this.arrTxtCaps)
            }
        },
        cTest (inp){
            var container = ''
            for (var i = 0 ; i < this.len; i++){
                container += inp[Math.floor(Math.random() * inp.length)] 
            }
            return container
        },
        Copy (){
            navigator.clipboard.writeText(this.Result);
        },
    },
    watch:{
        num(){
            if(this.Result)
            this.builder()
        },
        char(){
            if(this.Result)
            this.builder()
        },
        charCaps(){
            if(this.Result)
            this.builder()
        },
        symbol(){
            if(this.Result)
            this.builder()
        }
    }
}
</script>
<template>
    <div class="container">
        <div class="panelR">
            <div class="brand">cPass</div>
            <div>
                <div class="menuSection">
                    <div>عدد :</div>
                    <div><input type="checkbox" v-model="num"></div>
                </div>
                <div class="menuSection">
                    <div>حرف :</div>
                    <div><input type="checkbox" v-model="char"></div>
                </div>
                <div class="menuSection">
                    <div>حرف بزرگ :</div>
                    <div><input type="checkbox" v-model="charCaps"></div>
                </div>
                <div class="menuSection">
                    <div>کاراکتر :</div>
                    <div><input type="checkbox" v-model="symbol"></div>
                </div>
                <div class="menuSection menuLength">
                    <div>طول رمز :</div>
                    <div><input type="number" class="lenPass" v-model="len"></div>
                </div>
            </div>
            <div class="bottomBtn"><button @click="builder" class="builder">ساخت</button></div>
        </div>
        
        <div class="cadrC">
            <div class="displayCadr">
                <input disabled type="text" class="output" :class="Result ? 'bb' : ''" placeholder="نمایش پسورد" @click="inp" v-model="Result"/>
                <div class="btns">
                    <button class="copy" @click="Result = ''">پاک کردن</button>
                    <button class="copy" @click="Copy">کپی</button>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Titan+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono&display=swap');
button{
    background: #E3E8E9;
    border:none;
    margin:1px;
    font-size:17px;
    border-radius:2px;
    font-family:irSans;
    padding: 2px 6px;
    cursor:pointer;
    outline:none;
}
input{
    font-family:irSans !important;
}
input[type=text]{
    cursor:text;
}
.brand{
    text-align: center;
    margin-top: 5px;
    font-size: 29px;
    font-family: 'Titan One', cursive;
    color:#ff780a;
}
.container{
 display: flex;
 height: 100vh;
}
.panelR{
  background-color:#bcbcbc57;
  width: 337px;
  margin:20px;
  border-radius: 10px;
  display: grid;
  grid-template-rows: 1fr 8fr 1fr;
}
.cadrC{
  width: 100%;
  margin: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.menuSection{
    display: grid;
    grid-template-columns: 4fr 1fr;
    padding: 0 15px;
    margin-top: 20px;
}
.lenPass{
    width: 50px;
    font-size: 16px;
    outline: none;
}
.bottomBtn{
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
}
.builder{
    display: block;
    width: 90%;
    padding: 10px;
    margin: 10px auto;
    background-color: #ff780a;
    border-radius: 5px;
}
.displayCadr{
    background-color:#bcbcbc57;
    padding: 50px;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.menuLength {
    grid-template-columns: 2fr 1fr;
    margin-top: 50px;
}
.output{
    font-size: 18px;
    background-color:#fff0;
    border: none;
    border-bottom: 1px solid #00000082;
    border-radius: 6px;
    padding: 6px;
    outline:none;
    color:#fff;
    font-family: 'Roboto Mono', monospace !important;
    transition:.2s ease all;
}
.output::placeholder{
    color:#fff;
}
.btns{
    display: flex;
}
.copy{
    margin-top: 10px;
    flex-grow: 1;
}
.bb{
    border-bottom:1px solid #ff780a;
}
@media screen and (max-width:680px) {
    .container{
        flex-direction: column;
        align-items: center;
    }
    .cadrC{
        order:1;
        margin-top: 50px;
    }
    .panelR{
        order:2;
        grid-template-rows: 1fr 5fr 1fr;
        width: 90%;
    }
}
@media screen and (max-width:680px) and (min-height:694px) {
    .panelR{
        position: fixed;
        bottom: 0;
    }
    
}
</style>