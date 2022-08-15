# tuya-rele-WB2S-smart-switch-

<p>
Configure tuya switch OpenBK7231N
</p>
<img src="https://github.com/Alexxx113/tuya-rele-WB2S-smart-switch-/blob/main/IMG_20220717_025042.jpg" alt="альтернативный текст" />
<img src="https://github.com/Alexxx113/tuya-rele-WB2S-smart-switch-/blob/main/IMG_20220717_025051.jpg" alt="альтернативный текст" />
<p></p>



<img src="https://github.com/Alexxx113/tuya-rele-WB2S-smart-switch-/blob/main/rele%20uart.jpg" alt="альтернативный текст" />

<p></p>
<b>Flashing for <red>BK7231N</red></b>
<p></p>
<p>Go to pages firmware instruction</p>


<a href="https://github.com/openshwprojects/OpenBK7231T_App">OpenBK7231T_App</a>

<p></p>
<p>connect uart 3.3v !!!!</p>

<a href="https://github.com/OpenBekenIOT/hid_download_py">Python bk flasher</a>

<p>Flash BK7231N QIO binary, like that:</p>

<p>python uartprogram W:\GIT\OpenBK7231N\apps\OpenBK7231N_App\output\1.0.0\OpenBK7231N_app_QIO_1.0.0.bin --unprotect -d com10 -w --startaddr 0x0</p>

<p></p>
<p>conect new WIFI "openbk..."</p>
<p>go "192.168.4.1"</p>
<p>configure WIFI</p>

<p></p>
<b>configure module:</b>
<p></p>
<p>P7 wifi_led_n 0</p>
<p>P24 rel 1</p>
<p>P26 btn 1</p>

<p>configure MQTT</p>

<b>home assistant config:</b>
<p>"name" = name switch</p>

<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="">
  <pre class="notranslate">
  <code>
light:
  - platform: mqtt
    unique_id: "name"
    name: "name"
    state_topic: ""name"/1/get"
    command_topic: ""name"/1/set"
    qos: 1
    payload_on: 1
    payload_off: 0
    retain: true
    availability_topic: ""name"/connected"
  </code>
  </pre>
</div>



