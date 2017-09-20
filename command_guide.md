============================================================================================================
------------------------------------------ PENDRIVES COMPATÍVEIS -------------------------------------------
============================================================================================================
> Patriot 8GB Supersonic Xpress (with PS2251-03 (2303) controller)
> Kingston DataTraveler 3.0 T111 8GB
> Verbatim STORE N GO V3 8GB USB 3.0 (May ship with 2307)

============================================================================================================
------------------------------------------ PREPARANDO OS ARQUIVOS ------------------------------------------
============================================================================================================
INSTALAR sdcc-3.4.0-x64-setup.exe

EDITAR COMANDOS EM: C:\Psychson\duckGO\comandos.txt

GERAR ARQUIVO inject.BIN >>>>
	Versão GUI: C:\Psychson\duckGO\duckencodergui.jar
	ou: cd C:\Psychson\duckGO\ & java -jar duckencoder.jar -i comandos.txt -o inject.bin -l ptBR.properties

INJETAR ARQUIVO .bin NO FIRMWARE >>>>
	
	1 Passo - Gerar firmware.bin: Em C:\Psychson\firmware" Executar BUILD.bat (ja esta pronto > backupFirmwareOk.bin)
	
	2 Passo - Efetuar inject no firmware .bin:
		C:\Psychson\tools\EmbedPayload.exe C:\Psychson\duckGO\inject.bin C:\Psychson\firmware\firmware.bin
		A partir de agora firmware.bin não é mais o original.

=================================================================================================================
-------------------------------------- GRAVANDO FIRMWARE NO PENDRIVE --------------------------------------------
=================================================================================================================
OBS: Só funciona se o pendrive estiver com o firmware original!!! Caso contrario, pode não funcionar e o pendrive deve ser restaurado...
OBS: Se o programa MPALL_F1_0702_v363_00.exe não funcionar deve ser restaurado com os comandos abaixo, porém deve se saber a letra do drive.

SETANDO O PENDRIVE EM BOOTMODE (**luz acesa, não pisca)>>>>
	C:\Psychson\tools\DriveCom.exe /drive=F /action=SetBootMode

SETANDO O PENDRIVE EM MODO SendExecutable COM O BURNER .bin (luz apaga)>>>>
	C:\Psychson\tools\DriveCom.exe /drive=F /action=SendExecutable /burner=C:\Psychson\fwburner\BN03V104M.BIN

GRAVANDO O FIRMWARE PAYLOAD NO PENDRIVE >>>>
	C:\Psychson\tools\DriveCom.exe /drive=F /action=SendFirmware /burner=C:\Psychson\fwburner\BN03V104M.BIN /firmware=C:\Psychson\firmware\firmware.bin
_________________________________________________________________________________________________________________
SALVANDO O FIRMWARE ORIGINAL (opcional) >>>>
	C:\Psychson\tools\DriveCom.exe /drive=F /action=DumpFirmware /firmware=c:\currentfirmware.bin

=================================================================================================================
em breve badusb para digispark :)
