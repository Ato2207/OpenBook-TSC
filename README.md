# OpenBook-TSC

# 1. Diagrama bloc
![Block Diagram OpenBook](https://github.com/user-attachments/assets/f189ee1a-4e98-45da-940b-bce0bc9feab5)

# 2. Bill Of Materials (BOM)
| Nr. | Componentă                 | Cantitate | Link achiziție | Datasheet |
|----|-----------------------------|----------|-----------------|-----------|
| 1  | ESP32-C6-WROOM-1-N8         | 1        | [Mouser](https://ro.mouser.com/ProductDetail/Espressif-Systems/ESP32-C6-WROOM-1-N8?qs=8Wlm6%252BaMh8ST02Gmwp74cw%3D%3D) | [Datasheet](https://ro.mouser.com/datasheet/2/891/Espressif_ESP32_C6_WROOM_1__Datasheet_V0_1_PRELIMI-3239987.pdf) |
| 2  | Regulator de tensiune 3.3V  | 1        | [Mouser](https://www.mouser.co.uk/ProductDetail/Torex-Semiconductor/XC6220A331MR-G?qs=AsjdqWjXhJ8ZSWznL1J0gg%3D%3D) | [Datasheet](https://www.mouser.co.uk/datasheet/2/760/xc6220-3371556.pdf) |
| 3  | Display                     | 1        | https://www.waveshare.com/7.5inch-e-paper-hat.htm | [Datasheet](https://files.waveshare.com/upload/6/60/7.5inch_e-Paper_V2_Specification.pdf) |
| 4  | Senzor BME688 | 1        | [Mouser](https://ro.mouser.com/ProductDetail/Bosch-Sensortec/BME688?qs=IS%252B4QmGtzzqQoVDscqwx3A%3D%3D)| [Datasheet](https://ro.mouser.com/datasheet/2/783/bst_bme688_fl000-2307034.pdf) |
| 5  | Baterie            | 1        | [Mouser](https://www.tme.eu/ro/details/accu-lp584174_cl/acumulatori/cellevia-batteries/l584174/)| [Datasheet](https://www.tme.eu/Document/e0683d8c34e6d878124489f71bffb6ee/cel0014.pdf) |
| 6  | Fuel Gauge         | 1        | [Mouser](https://ro.mouser.com/ProductDetail/Analog-Devices-Maxim-Integrated/MAX17048G%2bT10?qs=D7PJwyCwLAoGnnn8jEPRBQ%3D%3D) | [Datasheet](https://ro.mouser.com/datasheet/2/609/MAX17048_MAX17049-3469099.pdf) |
| 7  | Controller de incarcare   | 1       | [Mouser](https://ro.mouser.com/ProductDetail/Microchip-Technology/MCP73831T-2ACI-MC?qs=yUQqVecv4quJ3ICqm%2FGZxw%3D%3D)| [Datasheet](https://ro.mouser.com/datasheet/2/268/MCP73831_Family_Data_Sheet_DS20001984H-3441711.pdf) |
| 8  | Butoane  | 3       | [Mouser](https://ro.mouser.com/ProductDetail/Panasonic/EVQ-Q2S03W?qs=WwqriLBepZso3gwmd6qd3A%3D%3D) | [Datasheet](https://4donline.ihs.com/images/VipMasterIC/IC/PANA/PANA-S-A0000770395/PANA-S-A0000770395-1.pdf?hkey=CECEF36DEECDED6468708AAF2E19C0C6) |
| 9  | Conector USB-C  | 1       | [Mouser](https://ro.mouser.com/ProductDetail/Amphenol-Commercial-Products/12401598E42A?qs=367PjNmvCmllVMBVyIyS3w%3D%3D) | [Datasheet](https://cdn.amphenol-cs.com/media/wysiwyg/files/documentation/datasheet/inputoutput/io_usb_type_c.pdf) |
| 10  | Conector card SD  | 1        | [Mouser](https://www.digikey.ro/en/products/detail/attend-technology/112A-TAAR-R03/17633923) | [Datasheet](https://www.attend.com.tw/data/download/file/112A-TAAR-R03_Spec.pdf) |
| 11  | RTC DS3231  | 1        | [Mouser](https://www.optimusdigital.ro/en/others/12402-ds3231-real-time-clock-module.html) | [Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/ds3231.pdf) |
| 12  | Memorie Flash 64MB externa  | 1        | [Mouser](https://ro.mouser.com/ProductDetail/Winbond/W25Q512JVEIQ?qs=l7cgNqFNU1jw6svr3at6tA%3D%3D) | [Datasheet](https://ro.mouser.com/datasheet/2/949/Winbond_W25Q512JV_Datasheet-3240039.pdf) |
| 13 | Tranzistoare  | 3      | - | - |
| 14 | Diode | 10      | - | - |
| 15 | Condensatori diversi  | 28       | - | - |
| 16  | Rezistente diverse          | 24  | -  | - |

# 3. Functionalitate Hardware
  ## 3.1 Componente
  - **ESP32-C6-WROOM-1-N8** – Microcontroler principal care gestionează comunicațiile (SPI, I2C, UART) și controlează perifericele.  
  - **Conector USB-C & Protecție ESD** – Permite alimentarea prin USB-C și protejează circuitul de descărcările electrostatice.  
  - **Controler de Încărcare MCP73831** – Reglează încărcarea bateriei Li-Po și gestionează curentul de alimentare.  
  - **Baterie Li-Po** – Asigură alimentarea de rezervă pentru funcționare independentă de sursa USB.  
  - **Regulator de Tensiune LDO** – Stabilizează alimentarea la 3.3V pentru microcontroler și componente auxiliare.  
  - **Memorie Flash NOR Externă (64MB)** – Stocare suplimentară pentru date.
  - **Modul RTC DS3231SN** – Oferă funcționalitate de ceas în timp real, suportând alarme și detectarea pierderii tensiunii..  
  - **Senzor Ambiental BME688** – Măsoară temperatura, umiditatea, presiunea și calitatea aerului. Comunicare prin I2C, cu suport pentru conectare rapidă (Qwiic/Stemma QT).  
  - **E-Paper Display Drive Circuit si Header** – Genereaza semnalele necesare pentru controlul ecranului E-Paper.
  - **Slot SD Card** – Permite stocarea locală a datelor și fișierelor de configurare. 
  - **Supervizor de Tensiune + Butoane Reset/Boot** – Monitorizează alimentarea și asigură resetarea sistemului atunci când este necesar.

  ## 3.2 Specificatii de comunicare
  - **I2C** – Utilizat pentru senzorul BME688 și modulul DS3231SN.
  - **SPI** – Folosit pentru NOR Flash, display-ul E-Paper și cardul SD.
  - **UART** – Disponibil pentru debugging sau conectarea altor module. 
  - **Wi-Fi & Bluetooth LE** – Furnizate de ESP32-C6 pentru conectivitate wireless.

# 4. Pini ESP32-C6-WROOM-1-N8 si utilizare
| Pin ESP32-C6| Funcție              | Modul de utilizare                                     |
|-------------|----------------------|--------------------------------------------------------|
| **3V3**     | Supply               | Furnizează tensiune de 3.3V pentru componente.         |
| **GND**     | Ground               | Referință pentru circuit.                              |
| **EN**      | Enable               | Permite pornirea/resetarea modulului (tensiune ridicată = activ). |
| **IO0**     | Interrupt            | Pentru notificari, conectat la modulul RTC.            |
| **IO1**     | RTC CLK              | Semnal de ceas pentru modulul RTC.                     |
| **IO2**     | SPI MISO             | Primire date de la periferice conectate prin SPI.      |
| **IO3**     | Status               | Semnalizeaza starea de ocupay a display-ului.          |
| **IO4**     | Slave Select         | Selecteaza cardul SD.                                  |
| **IO5**     | Data/Command         | Selecteaza intre modul de date si comenzi.             |
| **IO6**     | SPI CLK              | Semnal de ceas pentru SPI.                             |
| **IO7**     | SPI MOSI             | Transfer date catre periferice conectate prin SPI.     |
| **IO8**     | GPIO                 | Pin general GPIO.                                      |
| **IO9**     | Boot                 | Conectat la un buton pentru intrarea in modul de boot. |
| **IO10**    | Chip Select          | Activeaza comunicarea cu display-ul.                   |
| **IO11**    | Chip Select          | Activeaza comunicarea cu memoria flash.                |    
| **IO12**    | USB_D-               | Pentru USB.                                            |
| **IO13**    | USB_D+               | Pentru USB.                                            |
| **IO15**    | Change               | Conectat la un buton.                                  |
| **IO16**    | TX                   | Pentru UART.                                           |
| **IO17**    | RX                   | Pentru UART.                                           |
| **IO18**    | RTC_RST              | Pentru resetarea modulului RTC.                        |
| **IO19**    | I2C_PW               | Supply pentru I2C.                                     |
| **IO20**    | EPD_3V3_C            | Alimentare display.                                    |
| **IO21**    | SDA                  | Linia de date pentru I2C.                              |
| **IO22**    | SCL                  | Semnalul de ceas pentru I2C.                           |
| **IO23**    | EPD_RST              | Pentru resetarea display-ului.                         |

  
  
  
