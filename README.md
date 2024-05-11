# EDGE--CP2
Checkpoint 2 de EDGE, sistema para verificação de temperatura, umidade e luminosidade de uma vinheria. 
Grupo: NJ Tech
<table>
  <tr>
    <th>Nomes</th>
    <th>Rm</th>
  </tr>
  <tr>
    <td>Gustavo Pierre</td>
    <td>558928</td>
  </tr>
  <tr>
    <td>Gabriel Belo</td>
    <td>551669</td>
  </tr>
  <tr>
    <td>Enzo Dias</td>
    <td>558225</td>
  </tr>
  <tr>
    <td>Arthur Abonizio</td>
    <td>555506</td>
  </tr>
</table>

<h1>Link Para o projeto</h1>
https://wokwi.com/projects/397483223723166721



<h1>Materiais:</h1>
<ul>
  <li>Arduin Uno</li>
  <li>Breadboard</li>
  <li>LCD 16x2</li>
  <li>4x resistors</li>
  <li>3x LED's</li>
  <li>Photoresistor (LDR) Sensor</li>
  <li>DHT22</li>
  <li>Buzzer</li>
</ul>



<h1>Foto do sistema:</h1>
<img src="https://github.com/gabriel-belo/EDGE--CP2/assets/126474319/76188a39-0186-4587-8c9b-e5d431bc4198"/>



<h1>Descrição:</h1>
O sistema é desenvolvido com um Arduino Uno visando o monitoramento ambiental. Para a coleta de dados foram utilizados dois sensores o DHT22 e o Photoresistor (LDR), o DHT22 coletando a umidade e temperatura do ambiente e o Photoresistor capitando a luminosidade. Para informar o estado do ambiente utilizamos três LED's das cores verde, amarelo e vermelho que representam o estado ideal, estado de cuidado e fora dos padrões respectivamente. O LCD apresenta os dados em tempo real, sendo a temperatura em graus celsius e uma infromação se é ideal ou não a umidade em porcentagem e uma infromação se é ideal ou não e a luminosida usando três padrões: luminosidade ideal, ambiente a meia luz e ambiente muito claro e também tem a utilização do Buzzer que é acionado nos estados de cuidado e fora dos padrões.
O código inicia com a importação das bibliotecas LiquidCrystal e DHT,então os pinos de conexão para os componentes são configurados e as variaveis necessárias são criadas para interagir com eles.
O void loop inicia com a definição do pino analógico do Photoresistor para leitura da luminosidade, e em seguida vem os cálculos que transformam os dados do LDR para a medida ideal a ser usada. Então temos duas variaveis temperatura e umidade que respectivamente contém as funções readTemperature() e readHumidity(). Com base nos dados coletados, desenvolvemos três condições fundamentais.

<ol>
  <li>Estado ideal: Os padrões para está condição são: luminosidade menor ou igual a 350, temperatura de 10 a 15 graus Celsius, e umidade de 50% a 70%. Com essas condições o sistema ativa o LED verde para confirmar as condições ideais e mostra no display LCD a temperatura e uma confirmação de que está dentro das medidas ideais e a umidade e uma conrfirmação do estado ideal.</li>
  <li>Estado de cuidado: Nesta condição os padôes são: luminosidade maior que 350 e menor ou igual a 450 OU temperatura acima do limite ideal de 15 ou abaixo de 10 graus Celsius. Quando estas situações são identificadas, o sistema aciona o LED amarelo, produz um som de aviso com o Buzzer e mostra no display LCD na ordem luminosidade e depois temperatura qual o dado que está fora dos padrões junto do seu valor.</li>
  <li>Fora dos padrões: Intensidade luminosa alta maior 450 ou níveis de umidade abaixo de 50% ou acima de 70% não estão dentro da faixa ideal.Neste bloco de código, o sistema acende um LED vermelho, emite um alarme com o Buzzer e mostra no display LCD na ordem luminosidade e depois umidade qual o dado que está fora dos padrões junto do seu valor.</li>
</ol>
 
Além disso, todas as notificações são enviadas através da porta serial para permitir monitoramento adicional, resultando em um sistema total de monitoramento ambiental com feedback visual e sonoro em tempo real.


