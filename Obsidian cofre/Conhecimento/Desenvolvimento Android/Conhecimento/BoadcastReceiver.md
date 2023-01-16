Eles vão receber broadcasts.

**Exemplo:** saber quando o dispositivo entrou em modo avião, quando está carregando, no Wifi ou qualquer outro [[Intent]]. O BroadcastReceiver vai receber e lidar com o intent de forma assíncrona, mas ele não foi feito para rodar durante muito tempo. Ele deve encaminhar a mensagem para um [[Service]]. **BroadcastReceiver** pode ser registrado no **[[Manifest]]** ou ate mesmo em uma **[[Activity]]**.

-   Quando registrado em uma activity ele vai viver enquanto a Activity viver.

-   Quando registrado no manifest, ele vai viver independente de ter uma activity.

**Ponto importante:** Um BroadcastReceiver, dentro do `onReceive()` nao pode levar mais de 5 a 10 segundos para processar algo. O Android vai disparar um crash. Isso ta na [documentação](https://developer.android.com/reference/android/content/BroadcastReceiver).