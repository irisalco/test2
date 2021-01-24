
<template>  
  <div class="container">
    <div id="p5Canvas"></div>
  </div>
</template>

<script>
import P5 from 'p5';

export default {
  data() {
    return {
      p5Canvas: null,
    }
  },
  created() {
    const sketch = p5 => {
        let w = 600;
        let h = 600;

        

        p5.setup = () => {
            p5.createCanvas(w, h);
        };

        p5.draw = () => {
            
            p5.changeBG(p5.mouseX, p5.mouseY);
            
           
            p5.ellipse(p5.mouseX, p5.mouseY, 100);

        };

        
        p5.changeBG = (x, y) => {
          let _x = p5.map(x, 0, w, 0, 255);
          let _y = p5.map(y, 0, h, 0, 255);
          p5.background(_x, _y, 33);
          ax[i - 1] = ax[i];
           ay[i - 1] = ay[i];
        }
        
    }

    this.p5Canvas = new P5(sketch, 'p5Canvas');
  },
  unmounted () {
    this.p5Canvas = null;
  },
}
</script>


<style scoped>
 #p5Canvas {
  width: 100vw;
  position: relative;
}

main {
  margin: 0 auto;
  width: 90vw;
}
</style>
