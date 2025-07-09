# Клонирование репозитория
git clone 
cd epsylon-moscow-app

# Установка зависимостей
npm install

# Добавление платформы Android (если нужно)
cordova platform add android

# Запуск на эмуляторе
cordova emulate android

# Сборка релизной версии
cordova build android --release

# Иконки
https://iconnaut.com/android.php#ready


## Либа для подписи
sudo apt install openjdk-17-jre-headless

### Сгенерируйте ключ загрузки, которым вы подпишите приложение в формате AAB
keytool -genkey -v -keystore moscow.keystore -alias moscow -keyalg RSA -keysize 2048 -validity 10000

### Подписываем
https://console.rustore.ru/apps/2063609920/sign-key

java -jar pepk.jar --keystore moscow.keystore --alias moscow --output pepk_out.zip --encryptionkey=0000455857ae708210f08e63849e8333a05044f0d4ab8c9acd4f8ebf9ec4953d64f6890dde34e00ae2aa7b7b2f823b6f2be1b81020555d158e2032c196eba75f4f9d6b37 --include-cert

## Генерируем rem
keytool -exportcert -alias moscow -keystore moscow.keystore -rfc -file moscow.pem

## Ключ для переменных

base64 moscow.keystore > moscow.keystore.base64
cat moscow.keystore.base64


