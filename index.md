
<style>
@import("Alpha.ttf");

.board{
  position:absolute;
  top:50%;
  left:50%;
  transform: translate(-50%,-50%);
  box-shadow: 0px 0px 44px 0px rgba(0,0,0,0.75);
  
  width:400px;
  height:400px;
  background:whitesmoke;
}.tile{
  display:inline-block;
  height: 12.5%;
  width:12.5%;
  overflow:hidden;
}.even{
   background:#6b5b27;
}.odd{
   background:whitesmoke;
}.player{
  display:inline-block;
  width:100%;
  height:100%;
  font-size:25px;
  
  
  text-align:center;
  line-height: 200%;
}
</style>

<div class='board' id='board'>
  
</div>

<div class='king'>
  </div>
<script>

var odd = false;

for(i=0;i<64;i++){
  var tile  = document.createElement('div');
  tile.classList.add('tile')
  tile.id = "tile_"+i;
  
    
    if((i+1) % 8 == 0 && i != 0 && i!= 63){
      
      
      var tile2  = document.createElement('div');
      tile2.classList.add('tile');
      
      if(odd==false){
        tile.classList.add('even');
        tile2.classList.add('even');
        odd = true;
      }else{
        tile.classList.add('odd');
        tile2.classList.add('odd');
         odd = false;
      }
      
      tile.classList.add('double');
        tile2.classList.add('double');
        
        tile.id = "tile_"+(i+1);
        
        tile2.id = "tile_"+i;
      
      i++;
      document.getElementById('board').append(tile2);
    }else{
      
      
      if(odd==false){
        tile.classList.add('even');
        odd = true;
      }else{
        tile.classList.add('odd');
        odd = false;
      }
      
    }
  
  
  document.getElementById('board').append(tile);
}

restart()


function restart(){
  
  //Basic Soldiers
  
  for(i=0;i<8;i++){
    document.getElementById("tile_"+(i+48)).innerHTML = '<div class="player">&#9817;</div>';
  }
  
   for(i=0;i<8;i++){
    document.getElementById("tile_"+(i+8)).innerHTML = '<div class="player">&#9823;</div>';
  }
  
  
  //Set Castles
  
  document.getElementById("tile_63").innerHTML = '<div class="player">&#9814;</div>';
  document.getElementById("tile_56").innerHTML = '<div class="player">&#9814;</div>';
  
  document.getElementById("tile_0").innerHTML = '<div class="player enemy">&#9820;</div>';
  document.getElementById("tile_7").innerHTML = '<div class="player enemy">&#9820;</div>';
  
  
  //Set horses
  
  document.getElementById("tile_62").innerHTML = '<div class="player">&#9816;</div>';
  document.getElementById("tile_57").innerHTML = '<div class="player">&#9816;</div>';
  
  document.getElementById("tile_1").innerHTML = '<div class="player enemy">&#9822</div>';
  document.getElementById("tile_6").innerHTML = '<div class="player enemy">&#9822;</div>';
  
  
  //Set Bishops
  
  document.getElementById("tile_61").innerHTML = '<div class="player">&#9815;</div>';
  document.getElementById("tile_58").innerHTML = '<div class="player">&#9815;</div>';
  
  document.getElementById("tile_2").innerHTML = '<div class="player enemy">&#9821;</div>';
  document.getElementById("tile_5").innerHTML = '<div class="player enemy">&#9821;</div>';
  
  
  //Set Queens
  document.getElementById("tile_60").innerHTML = '<div class="player">&#9813;</div>';
  
  document.getElementById("tile_3").innerHTML = '<div class="player enemy">&#9819;</div>';
  
  //Set Kings
  
  document.getElementById("tile_59").innerHTML = '<div class="player">&#9812;</div>';
  
  document.getElementById("tile_4").innerHTML = '<div class="player enemy" nam>&#9818;</div>';
  
}
</script>
