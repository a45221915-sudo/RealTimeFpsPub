[English](../../README.md) | [Español](../es/README.md)
| <u>[Português](README.md)</u> | [Bahasa Indonesia](../in/README.md)
| [Русский](../ru/README.md) | [中文 (简体)](../zh-rCN/README.md) | [中文 (繁體)](../zh-rTW/README.md)
| [日本語](../ja-rJP/README.md) | [Tiếng Việt](../vi/README.md)
| [Türkçe](../tr/README.md)
| [हिन्दी](../hi/README.md) | [বাংলা (ভারত)](../bn-rIN/README.md) | [ਪੰਜਾਬੀ (ਭਾਰਤ)](../pa-rIN/README.md) | [తెలుగు](../te-rIN/README.md) | [اردو (پاکستان)](../ur-rPK/README.md) | [العربية](../ar/README.md) | [ไทย](../th/README.md)

----------------------

### TL;DR

* Executa `adb shell appops set com.tribalfs.realtimefps PROJECT_MEDIA allow`.
* Se estiveres a usar uma aplicação de terminal Android com permissões elevadas, executa  
  `pm grant com.tribalfs.realtimefps android.permission.PROJECT_MEDIA`.

----------------------

Conceder permissão usando um PC:
----------------------

<details>

### 1. Ativar o modo de programador nas definições do telemóvel

<details>

* Vai a _Definições_ > _Acerca do telefone_ > _Informações de software_ e toca várias vezes em
  _Número da compilação_  
  até que o modo de programador seja ativado.

  <img src="res/about_phone.jpg" width=320 height=640 alt="sobre o telefone">

</details>

### 2. Ativar a depuração USB

<details>

* Vai a _Definições_ > _Opções de programador_ (pode ser _Definições_ > _Sistema_ > _Opções de
  programador_ em versões mais antigas do Android),  
  desce até encontrar a opção _Depuração USB_.

  <img src="res/usb_debugging.jpg" width=320 height=600 alt="adb">

#### Notas para alguns dispositivos como MIUI:

* Ativa também a opção _Depuração USB para Definições de Segurança_ se estiver disponível em Opções
  de programador.

* Ativa a opção _Desativar monitorização de permissões_ se estiver presente. É necessário reiniciar
  o dispositivo.

</details>

### 3. Fazer o download do ADB no computador

<details>

* Faz download do ADB (platform-tools) para o teu computador:  
  para [Windows](https://dl.google.com/android/repository/platform-tools-latest-windows.zip) |  
  para [Mac](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip) |  
  para [Linux](https://dl.google.com/android/repository/platform-tools-latest-linux.zip)

* Extrai o ficheiro ZIP descarregado.

</details>

### 4. Navegar até dentro da pasta acede à pasta

`platform-tools` que extraíste no Explorador do Windows ou Finder (macOS)

### 5. Abrir o terminal de comandos

<details>

#### Para Windows: abrir o CMD

* Escreve `cmd` na barra de endereço e pressiona Enter. Isto abrirá o Prompt de Comando do Windows.

  ![opening_cmd](res/opening_cmd.png)

#### Para macOS:

* Faz duplo clique no ficheiro zip descarregado para abri-lo, clica com o botão direito na pasta
  `platform-tools` para abrir o menu de contexto e depois clica em _Serviços_ > _Novo Terminal na
  Pasta_.

</details>

### 6. Ligar o telemóvel ao computador

<details>

* O teu telemóvel mostrará um aviso _Permitir depuração USB_ na primeira ligação em modo de
  depuração.  
  Toca em _Permitir_ ou _OK_.
* Podes marcar _Permitir sempre a partir deste computador_ (ver nota no final sobre manter a
  depuração USB ativada).

  <img src="res/usb_debugging_prompt.jpg" width=320 height=640 alt="adb prompt">

* Verifica a ligação introduzindo o seguinte comando e pressionando Enter.  
  Deverá mostrar o ID do dispositivo se estiver ligado com sucesso.

> ```adb devices```

![6](res/adb_devices.png)

* Se o teu dispositivo não se ligar, tenta outra porta USB e/ou outro cabo de dados.  
  Se ainda assim não funcionar, o computador pode estar a faltar o driver USB do dispositivo.  
  Consulta [aqui os drivers OEM USB](https://developer.android.com/studio/run/oem-usb#Drivers).  
  Após instalar, reinicia o PC e repete o passo 6.

</details>

### 7. Conceder a permissão PROJECT_MEDIA ao Real-time FPS Monitor

<details>

* Quando estiver ligado corretamente, introduz o seguinte comando e pressiona Enter.  
  Podes copiar o comando abaixo. Se for executado corretamente, não mostrará nenhum resultado.

> ```adb shell appops set com.tribalfs.realtimefps PROJECT_MEDIA allow```

* Se aparecer `adb.exe: more than one device/emulator...`, executa o seguinte comando:

>
```adb -s [ID do dispositivo mostrado no passo 6] shell appops set com.tribalfs.realtimefps PROJECT_MEDIA allow```

![6](res/PROJECT_MEDIA.png)

#### Nota para MIUI, OnePlus e outros dispositivos

Se aparecer o erro `java.lang.SecurityException: grantRuntimePermission`, segue estes passos:

1. Vai a _Definições_ > _Opções de programador_ (ou _Definições_ > _Sistema_ > _Opções de
   programador_)
2. Desce até encontrar e ativa **Depuração USB (Definições de Segurança)**
3. Se aparecer algum _Aviso de Cautela_, segue as instruções indicadas.
4. Reinicia o dispositivo e repete os passos da Secção 7.

**Está feito!**
</details>

#### Agora podes desativar a depuração USB

* Vai a _Definições_ > _Opções de programador_, desce e **desativa** a opção _Depuração USB_.

</details>

----------------------

Conceder permissão sem usar um PC (usando Shizuku):
----------------------
<details>

### Opção 1: Podes instalar [Shizuku](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api)*

e ativá-lo seguindo o guia fornecido. Depois, volta à aplicação _Real-time FPS Monitor_ para
conceder a permissão
aplicando uma resolução.

*Se a versão da Play Store não funcionar no teu dispositivo, podes usar
esta [fork do Shizuku](https://github.com/thedjchi/Shizuku/releases) em vez disso.

</details>

----------------------

### Não precisas repetir este processo, a menos que desinstales completamente a aplicação e a voltes a instalar.
