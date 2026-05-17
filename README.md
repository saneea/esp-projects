# esp-projects

Some configs for esp32, esphome

## создать python virtual environment

```sh
python3 -m venv my-venv
```

## активировать python virtual environment

```sh
source ./my-venv/bin/activate
```

## деактивировать python virtual environment

```sh
deactivate
```

## установить утилиту esphome

```sh
pip install esphome
```

после установки может потребоваться деактивировать и снова активировать python virtual environment

## проверить версию esphome

```sh
esphome --version
```

## поискать в подключённых к USB дев-плату

```sh
ls /dev/tty* -al | grep USB
```

обычно девайс по usb называется /dev/ttyUSB0, но вроде может и /dev/ttyACM0

## прошить девайс через USB

```sh
esphome run ./my-esphome-config.yaml --device /dev/ttyUSB0
```

## прошить девайс "по воздуху", т.е. OTA (Over-The-Air)

можно и без `--device`, тогда автоматом по имени будет определять по хостнэйм в lan сети ip девайса

```sh
esphome run ./my-esphome-config.yaml --device 192.168.1.243
```

## скомпилировать прошивку

```sh
esphome compile ./my-esphome-config.yaml
```

скомпилированная прошивка будет расположена в файле `./.esphome/build/<project-name>/.pioenvs/<project-name>/firmware.ota.bin`. Загрузить её потом можно через веб-интерфейс

## смотреть логи девайса

```sh
esphome logs ./my-esphome-config.yaml
```

так же как и для команды `run` можно указывать параметр `--device`

можно опционально указать уровень логирования так ('DEBUG', 'INFO', 'WARNING', 'ERROR', 'CRITICAL')

```sh
esphome -l INFO logs ./saneea-esp.yaml
```

# генерация ключа в base64 для api.encryption.key

```sh
python3 -c "import os, base64; print(base64.b64encode(os.urandom(32)).decode())"
```

или так

```sh
openssl rand -base64 32
```
