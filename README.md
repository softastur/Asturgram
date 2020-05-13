# Asturgram p'Android

[Telegram](https://telegram.org) ye una aplicación de mensaxería que s'enfoca na velocidá y seguranza. Ye superrápida, cenciella y llibre.

Esta bifórcación non oficial básase en [Telegram-FOSS](https://github.com/Telegram-FOSS-Team/Telegram-FOSS) qu'al empar tamién se basa na aplicación orixinal [Telegram App for Android](https://github.com/DrKLO/Telegram).

## Cambeos:

*Troquéu de binarios y/o códigu fonte sospechosos que nun cumplen colos principios FOSS:*
- Compártese l'allugamientu con OpenStreetMap(osmdroid) en cuentes de Google Maps
- Úsase'l conxuntu de fustaxes de Twemoji y non el d'Apple
- Google Play Services GCM trocóse pol serviciu push de Telegram
- Hai qu'amosar un avisu permanente nes versiones superiores a Oreo, entrugái a Google
- **SEGURANZA:** Les versiones vieyes de BoringSSL tróquense pol códigu más nuevu que se compila al empaquetar l'aplicación
- **SEGURANZA:** Les versiones vieyes de FFmpeg tróquense pol códigu más nuevu que se compila al empaquetar l'aplicación
- **SEGURANZA:** El libWebP integráu ta anováu

*Desaniciu de binarios y/o códigu fonte sospechosos xunto coles sos funcionalidaes que nun cumplen colos principios FOSS:*
- Escanéu de códigos de barres (Passport) y deteición facial de Google Vision
- Integración con Google Wallet y Android Pay
- Integración con Google Voice
- Informe de casques y anovamientos automáticos per HockeyApp
- Receición de códigos de verificación per Google SMS. Has teclexar los códigos a mano.

*Miscelánea:*
- Permítese afitar un proxy enantes d'aniciar sesión
- Amestóse l'habilidá d'analizar allugamientos col esquema d'enllaz `geo:<lla>,<llo>,<zoom>`
- Fórciase les previsualizaciones de mapes estáticos de Telegram

## Documentación de l'API y el protocolu

Manuales de l'API de Telegram (inglés): https://core.telegram.org/api

Manuales del protocolu MTproto (inglés): https://core.telegram.org/mtproto

## Compilación

**NOTA: Nun se sofita la compilación en Windows. ¡Usa GNU/Linux n'asturianu!**

**Importante:**

1. Percises el NDK d'Android, Go (Golang) y [Ninja](https://ninja-build.org/) pa compilar l'aplicación.

2. Nun escaezas incluyir los somódulos cuando clones:
      - `git clone --recursive https://github.com/softastur/Asturgram.git`

3. Compila les dependencies natives de FFmpeg y BoringSSL:
      - Vete a la carpeta `TMessagesProj/jni` y executa lo de darréu (defini los caminos al NDK y Ninja):

      ```
      export NDK=[CAMÍN_AL_NDK]
      export NINJA_PATH=[CAMÍN_A_NINJA]
      ./build_ffmpeg_clang.sh
      ./patch_ffmpeg.sh
      ./patch_boringssl.sh
      ./build_boringssl.sh
      ```

4. Si ques espublizar una versión modificada d'esta aplicación o de la oficial:
      - Deberíes consiguir **la to clave API** equí: https://core.telegram.org/api/obtaining_api_id y crear un ficheru nomáu `API_KEYS` nel direutoriu raigañu del códigu fonte.
        El conteníu debería vese asina:
        ```
        APP_ID = 12345
        APP_HASH = aaaaaaaabbbbbbccccccfffffff001122
        ```
      - Nun uses el nome nin el llogotipu de Telegram (avión de papel blancu nun círculu azul) o Asturgram (berrón nun círculu azul) na to aplicación
      - Curia bien de la privacidá y los datos de los tos usuarios
      - **Alcuérdate d'espublizar les modificaciones al códigu fonte pa cumplir coles llicencies, por favor**

El proyeutu pue compilase con Android Studio o dende la llinia de comandos con gradle:

`./gradlew assembleAfatRelease`

# Códigu anticuáu

El códigu d'esta rama estrémase muncho del que se venía emplegando. Si quies acceder al códigu anterior, tiéneslu equí: https://github.com/softastur/Asturgram/tree/C%C3%B3digu_anticu%C3%A1u
