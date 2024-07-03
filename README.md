# pjang
sketch.js
1
let campoIdade;
2
let campoFantasia;
3
let campoAventura;
4
​
5
function setup() {
6
  createCanvas(800, 400);
7
  createElement("h2", "Recomendador de filmes");
8
  createSpan("Sua idade:");
9
  campoIdade = createInput("5");
10
  campoFantasia = createCheckbox("Gosta de fantasia?");
11
  campoAventura = createCheckbox("Gosta de aventura?");
12
}
13
​
14
function draw() {
15
  background("white");
16
  let idade = campoIdade.value();
17
  let gostaDeFantasia = campoFantasia.checked();
18
  let gostaDeAventura = campoAventura.checked();
19
  let recomendacao = geraRecomendacao(idade, gostaDeFantasia, gostaDeAventura);
20
​
21
  fill(color(76, 0, 115));
22
  textAlign(CENTER, CENTER);
23
  textSize(38);
24
  text(recomendacao, width / 2, height / 2);
25
}
26
​
27
function geraRecomendacao(idade, gostaDeFantasia, gostaDeAventura) {
28
  if (idade >= 10) {
29
    if (idade >= 14) {
30
      return "O menino que descobriu o vento";
31
    } else {
32
      if (idade >= 12) {
33
        if(gostaDeFantasia || gostaDeAventura) {
34
          return "Homem aranha: no aranhaverso";          
35
        } else{
36
         return "Ladrões de bicicleta";
37
        }
38
      } else {
39
        if (gostaDeFantasia) {
40
          return "As aventuras de pi";
41
        } else {
42
          return "Depois da chuva";
43
        }
44
      }
45
    }
46
  } else {
47
    if (gostaDeFantasia) {
48
      return "A viagem de chihiro";
49
    } else {
50
      return "O feitiço do tempo";
51
    }
52
  }
53
}
54
​
