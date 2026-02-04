# 🟢 Green Elf - Hardware Macro System

O **Green Elf** é um sistema de automação híbrido que processa scripts de software e os converte em sinais de hardware puro. O diferencial é o suporte a múltiplos métodos de emulação e o uso de perfis de hardware customizados para máxima segurança.

## ⚙️ Métodos de Conexão Suportados
O firmware pode ser compilado de duas formas:
1.  **Direto (Sem Shield):** Conexão via cabo USB diretamente na placa (Leonardo/RP2040).
2.  **USB Host Shield:** Permite conectar um mouse físico no Shield, que filtra e injeta os comandos antes de enviar ao PC.

## 🛠️ Configuração do Ambiente (Essencial)
Para que o hardware seja reconhecido corretamente, você **deve** modificar os arquivos da sua Arduino IDE:

### 1. Modificação do `boards.txt`
* Localize o arquivo `boards.txt` na pasta de instalação do seu core (Arduino ou RP2040).
* Substitua as definições de `VID/PID` e `Product Name` pelas fornecidas na pasta `/setup` deste repositório. Isso garante que o Windows identifique a placa como um periférico gamer genérico.

### 2. Mapeamento SPI (Para uso com USB Shield)
Se estiver usando o Mini USB Host Shield no Arduino Leonardo/Micro, siga esta pinagem:

| Mini USB Host Shield | Arduino Leonardo/Micro | Função |
| :--- | :--- | :--- |
| **VCC** | 5V | Alimentação |
| **GND** | GND | Terra |
| **MOSI** | D16 (ICSP-4) | Dados SPI |
| **MISO** | D14 (ICSP-1) | Dados SPI |
| **SCK** | D15 (ICSP-3) | Clock SPI |
| **SS (CS)** | D10 | Select |



## 🚀 Compilação e Upload
1.  Abra o arquivo correspondente ao seu hardware (`GreenElf_Leonardo.ino` ou `GreenElf_RP2040.ino`).
2.  Certifique-se de que a biblioteca **USB Host Shield Library 2.0** está instalada se for usar o método com Shield.
3.  Selecione a placa modificada no menu `Ferramentas > Placa`.
4.  Clique em **Carregar**.

## ⚖️ Licenciamento e HWID
O Green Elf utiliza proteção baseada em HWID. A licença é vinculada ao hardware da máquina após a primeira execução do software de interface.
