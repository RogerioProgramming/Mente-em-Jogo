# Instalação e uso

## 1. Baixar o pacote

1. Baixe o ZIP da versão desejada em [Releases](../../releases).
2. Extraia todo o conteúdo para uma pasta local com permissão de escrita.
3. Mantenha juntos todos os arquivos da build para PC: o executável depende das pastas que o acompanham.

O pacote inclui o aplicativo do instrutor para Windows e o APK para Meta Quest 3.

## 2. Preparar o computador e o Meta Quest 3

1. Abra a pasta da build de PC e execute o arquivo `.exe` do aplicativo do instrutor.
2. Quando o Windows solicitar acesso à rede, permita-o em redes privadas.
3. Conecte o computador e o Quest à mesma rede local.
4. Para usar aplicativos externos à Meta Horizon Store, ative o **Modo Desenvolvedor** no Quest, utilizando uma conta verificada vinculada a uma equipe de desenvolvedor da Meta.
5. Conecte o Quest ao computador com um cabo USB-C que transmita dados e, dentro do headset, autorize a depuração USB.

Em Windows, instale os Oculus ADB Drivers se o headset não for reconhecido. Consulte o [guia oficial de configuração da Meta](https://developers.meta.com/vr/documentation/native/android/mobile-device-setup/).

## 3. Instalar o APK

### Meta Quest Developer Hub

1. Abra o Meta Quest Developer Hub (MQDH).
2. Conecte o Quest por USB e confirme que ele aparece como ativo.
3. Escolha a opção para instalar um APK e selecione o arquivo `.apk` extraído do pacote.

### ADB

Com Android Platform Tools ou MQDH instalado, abra um terminal na pasta do APK e execute:

```powershell
adb devices
adb install -r .\MenteEmJogo.apk
```

Substitua `MenteEmJogo.apk` pelo nome do arquivo distribuído. Se o estado aparecer como `unauthorized`, aceite o pedido de depuração USB dentro do headset.

## 4. Executar uma sessão

1. No Quest, abra a Biblioteca, selecione **Fontes desconhecidas** e inicie **Mente em Jogo**.
2. No computador, use a aplicação do instrutor para inserir o código de identificação do participante e escolher a atividade.
3. Na primeira utilização, realize a calibração da ancoragem dos elementos virtuais com o headset.
4. Após a calibração, entregue o headset ao participante e inicie a atividade pelo computador.
5. Ao final, consulte os resultados e exporte-os em JSON, CSV ou PDF.

## Solução de problemas

- **O Quest não aparece no MQDH ou no ADB:** teste outro cabo USB-C de dados, outra porta USB e, no Windows, instale os Oculus ADB Drivers.
- **`unauthorized` no ADB:** aceite a solicitação de depuração dentro do headset e execute `adb devices` novamente.
- **O aplicativo não aparece no Quest:** abra a Biblioteca e selecione **Fontes desconhecidas**.
- **PC e Quest não se conectam:** confirme que estão na mesma rede local e permita o aplicativo no firewall do Windows para redes privadas.
