# Preparando Disco com Windows 10 e SYSPREP para importar no AMIs da AWS



Em um dos projetos que trabalhei, foi necessário criar discos virtuais a partir de uma imagem do Windows 10 com SYSPREP. O grande desafio era criar um disco virtual para subir nas instancias de EC2 da AWS mas sem manter o GUID de softwares como antivirus da Trend Micro ApexOne , Endpoint Manager (Landesk) e o próprio Windows. Para isso seria necessário utilizar o recurso de AMIs da AWS, porque no projeto varias instâncias com Windows e imagem customizada seria criada, assim, a captura da imagem deveria partir de um sistema que nunca foi ligado com o SYSPREP do Windows. Neste artigo vou abordar o aprendizado durante essa experiência de criação de um disco virtual a partir dessa captura do Windows. 


# Método 1 - Formatando o Windows com HD secundário

Aqui formatamos um disco fisico já com a imagem customizada e SYSPREP do Windows. Após formatar o hard disk desligamos o computador e inciamos com uma midia de WinPE (Poderia utilizar modo de reparo com prompt de comando a partir do pendrive ou HirensBoot). Aqui as etapas são necessarias para garantir que o Windows não crie o mesmo GUID pra demais imagens na AWS.


# Método 2 - Formatando o Windows com VHD




Isso é necessário para garantir que o Windows não mantenha GUIDs da instalação padrão. 

Physical-to-Virtual (P2V)
Free Software Converter
StarWind - https://www.starwindsoftware.com/starwind-v2v-converter
Disk2vhd - https://docs.microsoft.com/en-us/sysinternals/downloads/disk2vhd



