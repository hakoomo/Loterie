<!doctype html>
<html>
   <head>
      <style>
         #cont{
            display:flex;
         }
         #grille{
            width:50%;
         }
         #ctirage{
            display:inline-block;
         }
         #tirage{
            height:220px;
            width:50%;
            text-align:right;
         }
         #bon{
            font:72pt monospace;
            margin:30px auto;
            text-align:center;
            visibility:hidden;
            background-color:#48C;
            color:#FFF;
            width:120px;
            height:120px;
            border-radius:100px;
            line-height:120px;
         }
         .bouton{
            width:26px;
            height:26px;
            text-align:center;
            font:11pt monospace;
            border:solid 1px #48C;
            display:inline-flex;
            align-items:center;
            justify-content:center;
            margin:3px;
            cursor:pointer;
            transition:all 0.3s ease;
         }
         .bouton:hover{
            background-color:#48C;
            color:#FFF;
            transform:scale(1.4);
         }
         .zbouton{
            width:26px;
            height:26px;
            text-align:center;
            font:11pt monospace;
            border:solid 1px #48C;
            background-color:#F8F8F8;
            display:inline-flex;
            align-items:center;
            justify-content:center;
            margin:3px;
            color:#48C;
         }
         .nbouton{
            width:26px;
            height:26px;
            text-align:center;
            font:11pt monospace;
            border:solid 1px #48C;
            display:inline-flex;
            align-items:center;
            justify-content:center;
            margin:3px;
            color:#000;
         }
         button{
            border:none;
            cursor:pointer;
            display:block;
            width:300px;
            background-color:#48C;
            padding:10px;
            font-size:13pt;
            color:#FFF;
            text-decoration:none;
            font-family:arial,sans-serif;
            margin:10px auto;
            margin-bottom:10px;
         }
         button:hover{
            opacity:0.8;
         }
      </style>
      <script>
         function init(btn){
            btn.style.display="none";
            i=1;
            nbr=0;
            choix=new Array();
            creerGrille();
         }
         function creerGrille(){
            t=setTimeout("creerGrille()",50);
            bouton=document.createElement("div");
            bouton.className="bouton";
            bouton.innerHTML=i;
            bouton.setAttribute("id",i);
            bouton.onclick=function(){
               ajouter(this);
            }
            document.getElementById("grille").appendChild(bouton);
            if(i%7==0){
               br=document.createElement("br");
               document.getElementById("grille").appendChild(br);
            }
            i+=1;
            if(i>49)
               clearTimeout(t);
         }
         
         function ajouter(ob){
            if(nbr<6){
               ob.style.visibility="hidden";
               nbouton=document.createElement("div");
               nbouton.className="nbouton";
               nbouton.setAttribute("id","ch"+nbr);
               nbouton.innerHTML=ob.textContent;
               document.getElementById("choix").appendChild(nbouton);
               choix[nbr]=ob.firstChild.nodeValue;
               nbr+=1;
               if(nbr==6)
                  ztirage();
            }
         }
         j=0;
         function ztirage(){
            setTimeout("ztirage()",100);
            if(j<6){
               zbouton=document.createElement("div");
               zbouton.className="zbouton";
               zbouton.innerHTML=0;
               zbouton.setAttribute("id","res"+j);
               document.getElementById("res").appendChild(zbouton);
               j+=1;
               if(j==6){
                  document.getElementById("bon").style.visibility="visible";
                  tirage();
               }
            }
         }
         index=0;
         rep=0;
         tab=new Array();
         itr=50;
         function tirage(){
            tx=setTimeout("tirage()",40);
            rep+=1;
            if(rep<itr){
               for(k=index+1;k<6;k++)
                  document.getElementById("res"+k).innerHTML=Math.ceil(Math.random()*49);

               v=Math.ceil(Math.random()*49);
               document.getElementById("res"+index).innerHTML=v;
               if(rep==itr-1){
                  if(tab.indexOf(v)==-1){
                     tab[index]=v;
                     for(k=0;k<6;k++){
                        if(document.getElementById("ch"+k).firstChild.data==tab[index]){
                           document.getElementById("ch"+k).style.backgroundColor="#48C";
						    document.getElementById("res"+index).style.backgroundColor="#48C";
							document.getElementById("ch"+k).style.color="#FFF";
                           document.getElementById("res"+index).style.color="#FFF";
                           document.getElementById("bon").innerHTML=parseInt(document.getElementById("bon").textContent)+1;
                        }
                     }
                  }
                  else
                     rep=itr-2;
               }
            }
            else{
               rep=0;
               index+=1;
               if(index==6){
                  clearTimeout(tx);
                  return false;
               }
            }
         }
      </script>
   </head>
   <body>
      <button onClick="init(this)">Commencer une partie</button>
      <div id="cont">
         <div id="grille"></div>
         <div id="tirage">
            <div id="ctirage">
               <div id="choix"></div>
               <div id="res"></div>
               <div id="bon">0</div>
            </div>
         </div>
      </div>
   </body>
</html>
