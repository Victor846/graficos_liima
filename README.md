<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard</title>

    <script src="https://cdn.jsdelivr.net/npm/chart.js@2.8.0"></script>

    <style>
        body{
            display: flex;
            flex-wrap: wrap;
        }
    </style>

</head>
<body>
    <figure>
        <canvas id="grafico1"></canvas>
    </figure>
    <figure>
        <canvas id="grafico2"></canvas>
    </figure>
    <figure>
        <canvas id="grafico3"></canvas>
    </figure>
    <script src="./grafico.js"></script>
   
    <script>
    function criaGrafico(idGrafico, dados, cor){
    var ctx = document.getElementById(idGrafico).getContext('2d');
 var chart = new Chart(ctx, {
    // The type of chart we want to create
    type: 'line',

    // The data for our dataset
    data: {
        labels: dados["Rótulox"],
        datasets: [{
            label: dados["indicador"],
            backgroundColor: cor,
            borderColor: cor,
            data: dados["dados"]
        }]
    },

    // Configuration options go here
    options: {}
 });
}

var dadosGrafico1 = {
    "indicador": "GTA 5 (em milhões)",
    "Rótulox": ['2014', '2015', '2016', '2017', '2018', '2019', '2020...'],
    "dados":[23, 21, 25, 19, 25, 35, 34]
}

criaGrafico("grafico1", dadosGrafico1, 'rgb(0, 204, 0)') 

var dadosGrafico2 = {
    "indicador": "The last of us (em milhões)",
    "Rótulox": ['2014', '2015', '2016', '2017', '2018', '2019', '2020...'],
    "dados":[14, 17, 23, 31, 15, 19, 22]
}
criaGrafico("grafico2", dadosGrafico2, 'rgb(255, 0, 0)')

var dadosGrafico3 = {
    "indicador": "FIFA (em milhões)",
    "Rótulox": ['2014', '2015', '2016', '2017', '2018', '2019', '2020'],
    "dados":[13, 16, 24, 25, 31, 28, 25]
}
criaGrafico("grafico3", dadosGrafico3, 'rgb(0, 255, 255)')

</script>

</body>
</html>
