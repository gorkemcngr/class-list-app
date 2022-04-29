<template>
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Class List App</title>
  </head>
  <body>
    <header>Class List App</header>
    <div class="container">
      <div class="class--list--app">
        <div class="card" :style="borderRadius" :class="borderStatus">
          <ul class="class-list">
            <li>
              <label>
                <input @click="Changecolor" class="mr-5" type="checkbox" />
                <span>Background Color</span>
              </label>
            </li>
            <li>
              <label>
                <input @click="AddBorder" class="mr-5" type="checkbox" />
                <span>Border</span>
              </label>
            </li>
            <li>
              <label>
                <input @click="ChangeRadius" class="mr-5" type="checkbox" />
                <span>Border Radius</span>
              </label>
            </li>
            <li>
              <label>
                <input  @click="ChangeWritingColor" class="mr-5" type="checkbox" />
                <span>Color</span>
              </label>
            </li>
            <li>
              <label>
                <input @click="ChangeFont" class="mr-5" type="checkbox" />
                <span>Font Bold</span>
              </label>
            </li>
            <li>
              <label>
                <input @click="ChangeItalic" class="mr-5" type="checkbox" />
                <span>Font Italic</span>
              </label>
            </li>
          </ul>

          <textarea  rows="5" :style="[color,writingColor,fontbold,fontItalic]" ></textarea>
        </div>
      </div>
    </div>
  </body>
</html>

</template>

<script>
export default {
    data() {
        return {
          color: {'background-color':'white'},
          writingColor:{'color':'black'},
          counter:0,
          counterWritingColor: 0,
          borderStatus:{borderC: false},
          borderCounter:0,
          fontbold:{'font-weight': 'normal'},
          fontCounter:0,
          fontItalic:{'font-style': 'normal'},
          italicCounter:0,
          borderRadius:{'border-radius': '0px'},
          radiusCounter:0
        }
    },
    methods: {
       Changecolor(){
         if(this.counter===1){
           this.color= {'background-color':'white'}
           this.counter--;
         }
         else{
           this.color ={'background-color':'pink'}
           this.counter++;
         }
       
         console.log(this.color);
         return this.color
       },
       ChangeWritingColor(){
          console.log("pink oldu");
         if(this.counterWritingColor===1){
           this.writingColor= {'color':'black'}
           this.counterWritingColor--;
         }
         else{
           this.writingColor ={'color':'orange'}
          
           this.counterWritingColor++;
         }
       },
       AddBorder(){
         if(this.borderCounter===1){
           
           this.borderStatus={borderC: false};
           this.borderCounter--;
         }
         else{
           this.borderStatus={borderC: true};
           this.borderCounter++;
         }
         
       },
       ChangeFont(){
         if(this.fontCounter===1){
           this.fontbold= {'font-weight':'normal'}
           this.fontCounter--;
         }
         else{
           this.fontbold ={'font-weight': 'bold'}
           this.fontCounter++;
         }
       },
       ChangeItalic(){
         if(this.italicCounter===1){
           this.fontItalic= {'font-style': 'normal'}
           this.italicCounter--;
         }
         else{
           this.fontItalic ={'font-style': 'italic'}
           this.italicCounter++;
         }
       },
       ChangeRadius(){
         if(this.radiusCounter===1){
           this.borderRadius= {'border-radius': '0px'}
           this.radiusCounter--;
         }
         else{
           this.borderRadius ={'border-radius': '30px'}
           this.radiusCounter++;
         }
       }
    }
}

</script>

<style >
@import 'assets/style.css';
</style>