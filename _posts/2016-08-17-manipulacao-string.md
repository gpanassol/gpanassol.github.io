## String

### Manipulação de String para formatação de horas

Essa semana tive um desafio bem legal pegar um valor de minutos e transforma-lo em horas. Basicamente eu recebo o valor 2.5m e transformo em 00:02:30. Veja:

2.5   = 00:02:30 <br/>
61.5  = 01:00:30 <br/>
121.5 = 02:01:30 <br/>

A solução que proponho é:

```
public static String getHoraFormatadaFromMinutosInteiro(String minutosInteiro){
    	
	String horas = "00";
	String minutos = "00";
	String segundos = "00";
	
	if(!HowMUtilities.isEmpty(minutosInteiro)){
	
		if(minutosInteiro.contains(".")){
			
			String[] split = minutosInteiro.split("\\.");
			
			int qtdMinuto = Integer.parseInt(split[0]);
			double qtdSegundos = Integer.parseInt(split[1]);
			qtdSegundos = 60 * (qtdSegundos / 10);
			
			if(qtdMinuto < 10){
				minutos = "0"+qtdMinuto;
			} else {
				
				if(qtdMinuto > 59){
					int qtdHoras = qtdMinuto / 60;
					int resto = (qtdMinuto % 60);
					
					horas = "0"+qtdHoras;
					
					if(resto < 10){
						minutos = "0"+resto;
					} else {
						minutos = ""+resto;
					}
					
				} else {
					minutos = ""+qtdMinuto;
				}
			}
			
			if(qtdSegundos < 10){
				segundos = "0"+qtdSegundos;
			} else {
				segundos = ValidaFormatos.fromBDNumber(""+qtdSegundos, 0) ;
			}
			
		} else {
			
			int qtdMinuto = Integer.parseInt(minutosInteiro);
			
			if(qtdMinuto < 10){
				minutos = "0"+qtdMinuto;
			
			} else if(qtdMinuto > 59) {
				
				int qtdHoras = qtdMinuto / 60;
				int resto = (qtdMinuto % 60);
				
				horas = "0"+qtdHoras;
				
				if(resto < 10){
					minutos = "0"+resto;
				} else {
					minutos = ""+resto;
				}
				
			} else {
				minutos = ""+qtdMinuto;
			}
		}
	}
	
	return horas+":"+minutos+":"+segundos; 
	
}
```

<!-- COMPARTILHAMENTO DE POST -->
<table width="100%" align="center">
        <tr>
                <td><p>Compartilhe</p></td>
        </tr>
        <tr>
                <td align="center" title="Facebook">
                        <a onclick="window.open(this.href, 'facebook-share','width=580,height=296');return false;" href="https://www.facebook.com/sharer/sharer.php?u=http://gpanassol.github.io/notes/nosql/" class="icon-facebook">
                                <img src="/assets/network/fc.png" width="50" height="50"/>
                        </a>
                </td>
                <td align="center" title="Twitter">
                        <a onclick="window.open(this.href, 'twitter-share', 'width=550,height=235');return false;" href="http://twitter.com/share?text=NoSQL&amp;url=http://gpanassol.github.io/notes/nosql/" class="icon-twitter">
                                <img src="/assets/network/twitter.png" width="50" height="50"/>
                        </a>
                </td>
                <td align="center" title="LinkedIn">
                        <a onclick="window.open(this.href, 'google-plus-share', 'width=490,height=530');return false;" href="https://plus.google.com/share?url=http://gpanassol.github.io/notes/nosql/" class="icon-google-plus">
                                <img src="/assets/network/google-plus.png" width="50" height="50"/>
                        </a>

                </td>
        </tr>
</table>