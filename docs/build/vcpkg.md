---
title: 'vcpkg: диспетчер пакетов C++ для Windows, Linux и macOS'
description: vcpkg — это диспетчер пакетов на базе командной строки, который существенно упрощает получение и установку библиотек C++ с открытым кодом в Windows, Linux и macOS.
ms.date: 07/06/2020
ms.technology: cpp-ide
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.openlocfilehash: 7131f301a22b2834b04ef932f3cee426b04dc7e5
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373636"
---
# <a name="vcpkg-a-c-package-manager-for-windows-linux-and-macos"></a>vcpkg: диспетчер пакетов C++ для Windows, Linux и macOS

vcpkg — это диспетчер пакетов на базе командной строки для C++. Он существенно упрощает получение и установку сторонних библиотек в Windows, Linux и macOS. Если в вашем проекте используются сторонние библиотеки, рекомендуем использовать vcpkg для их установки. Диспетчер vcpkg поддерживает как библиотеки с открытым исходным кодом, так и закрытые библиотеки. Все библиотеки в каталоге vcpkg для Windows были протестированы на совместимость с Visual Studio 2015, Visual Studio 2017 и Visual Studio 2019. На данный момент vcpkg поддерживает более 1900 библиотек в каталогах Windows, Linux и macOS. Сообщество C++ постоянно добавляет новые библиотеки в оба каталога.

## <a name="simple-yet-flexible"></a>Простота и гибкость

Вы можете загрузить источники и собрать библиотеку всего одной командой. vcpkg является проектом с открытым исходным кодом, доступным на сайте GitHub. Вы можете настроить свои закрытые клоны vcpkg любым удобным образом. Например, можно указать другие библиотеки или версии библиотек, отличные от находящихся в общедоступном каталоге. На одном компьютере можно использовать несколько клонов vcpkg. С помощью предпочтительных параметров компиляции каждый из них можно настроить для формирования настраиваемой коллекции библиотек. Каждый клон является автономной средой, в которой имеется собственная копия vcpkg.exe, работающая только с собственной иерархией. Диспетчер пакетов vcpkg не добавляется ни к каким переменным среды и не имеет зависимостей от Visual Studio или реестра Windows.

## <a name="sources-not-binaries"></a>Исходные, а не двоичные файлы

Для библиотек в каталоге Windows vcpkg скачивает исходные, а не двоичные файлы<sup>1</sup>. Он компилирует эти источники, используя самую последнюю найденную версию Visual Studio. В C++ важно, чтобы используемые библиотеки и код приложения компилировались с помощью того же компилятора той же версии. Использование vcpkg позволяет устранить или как минимум сильно уменьшить риск появления несовместимых двоичных файлов, способных привести к проблемам. В командах разработчиков, специализирующихся на определенной версии компилятора, один член команды может с помощью vcpkg скачать исходные файлы и скомпилировать набор двоичных файлов. Затем он может воспользоваться командой экспорта, заархивировать двоичные файлы и файлы заголовков и отправить их другим членам команды. Дополнительные сведения см. ниже в разделе [Экспорт скомпилированных двоичных файлов и файлов заголовков](#export_binaries_per_project).

Можно также создать клон vcpkg с закрытыми библиотеками в коллекции портов. Добавьте порт, который скачивает готовые двоичные файлы и файлы заголовков. Затем создайте файл *portfile.cmake*, который просто копирует эти файлы в нужное расположение.

<sup>1</sup> *Примечание. Для некоторых частных библиотек исходные файлы недоступны. В этих случаях vcpkg скачает готовые совместимые двоичные файлы.*

## <a name="installation"></a>Установка

Клонируйте репозиторий vcpkg из GitHub: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg). Его можно загрузить в любую папку. Это расположение будет *корневым каталогом* vcpkg. После скачивания перейдите в этот каталог в командной оболочке.

В корневом каталоге vcpkg запустите начальный загрузчик vcpkg:

- **`bootstrap-vcpkg.bat`** (Windows)
- **`./bootstrap-vcpkg.sh`** (Linux, macOS)

В Linux или macOS может потребоваться добавить префиксы к командам vcpkg с помощью **`./`** , как показано в следующих примерах. Эти команды следует выполнять из корневого каталога vcpkg.

## <a name="search-the-list-of-available-libraries"></a>Поиск в списке доступных библиотек

Чтобы узнать, какие пакеты доступны, в командной строке введите **`vcpkg search`** .

Эта команда перечисляет файлы управления во вложенных папках *vcpkg/ports*. Вы увидите примерно такой список:

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

Вы можете выполнить фильтрацию на основе шаблона, например **`vcpkg search ta`** :

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-local-machine"></a>Установка библиотеки на локальном компьютере

Получив название библиотеки с помощью **`vcpkg search`** , воспользуйтесь **`vcpkg install`** , чтобы загрузить библиотеку и скомпилировать ее. vcpkg использует файл портов (portfile) библиотеки в каталоге *ports*. Если триада не указана, vcpkg установит и скомпилирует триаду по умолчанию для целевой платформы: x86-windows, x64-linux.cmake или x64-osx.cmake.

Для библиотек Linux vcpkg требует наличия установленного gcc на локальном компьютере. На macOS vcpkg использует Clang.

Если в portfile указаны зависимости, vcpkg скачает и установит и их. После скачивания vcpkg выполнит сборку библиотеки с помощью той же системы сборки, которую использует библиотека. Предпочтительными являются проекты CMake и MSBuild (в Windows), но поддерживается также MAKE и любые другие системы сборки. Если диспетчеру vcpkg не удается найти указанную систему сборки на локальном компьютере, он скачивает и устанавливает ее.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

Для проектов CMake используйте `CMAKE_TOOLCHAIN_FILE`, чтобы сделать библиотеки доступными через `find_package()`. Например, в Linux или macOS:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake
```

Windows:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg\scripts\buildsystems\vcpkg.cmake
```

Некоторые библиотеки содержат устанавливаемые параметры. Например, при поиске библиотеки curl вы также увидите список поддерживаемых параметров в квадратных скобках:

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

В этом случае квадратные скобки **`[`** и **`]`** являются литералами, а не метасимволами.

Можно указать конкретный параметр для установки в командной строке. Например, чтобы установить библиотеки для curl с использованием серверной части SSL по умолчанию для Windows, используйте команду **`vcpkg install curl[ssl]:x86-windows`** . Эта команда устанавливает необходимые компоненты, включая основную библиотеку (если это необходимо):

```cmd
> vcpkg list
curl:x86-windows            7.68.0-3   A library for transferring data with URLs
curl[non-http]:x86-windows             Enables protocols beyond HTTP/HTTPS/HTTP2
curl[ssl]:x86-windows                  Default SSL backend
curl[sspi]:x86-windows                 SSPI support
curl[winssl]:x86-windows               SSL support (Secure Channel / "WinSSL")
zlib:x86-windows            1.2.11-6   A compression library
```

## <a name="list-the-libraries-already-installed"></a>Вывод списка уже установленных библиотек

После установки некоторых библиотек вы можете воспользоваться **`vcpkg list`** , чтобы увидеть, что у вас есть.

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

## <a name="integrate-with-visual-studio-windows"></a>Интеграция с Visual Studio (Windows)

### <a name="per-user"></a>Для каждого пользователя

Выполните команду **`vcpkg integrate install`** , чтобы настроить Visual Studio для поиска всех файлов заголовков и двоичных файлов vcpkg для каждого пользователя. При этом редактировать пути к каталогам VC++ вручную не требуется. При наличии нескольких клонов vcpkg клон, из которого выполняется эта команда, становится новым расположением по умолчанию.

Теперь вы можете добавлять файлы заголовков в #include, используя автозавершение, — для этого достаточно ввести папку или заголовок. Для связывания с библиотеками или добавления ссылок на проект выполнять какие-либо другие действия не требуется. На рисунке ниже показано, как Visual Studio находит файлы заголовков azure-storage-cpp. Средство vcpkg помещает файлы заголовков во вложенную папку *\installed* и распределяет их по целевым платформам. На следующей схеме показан список включаемых файлов во вложенной папке *\was* для библиотеки.

![vcpkg и IntelliSense](media/vcpkg-intellisense.png "vcpkg и IntelliSense")

### <a name="per-project"></a>Для каждого проекта

Если вам нужно использовать определенную версию библиотеки, которая отличается от версии в вашем активном экземпляре vcpkg, сделайте следующее.

1. Создайте клон vcpkg.
1. Измените portfile для библиотеки, чтобы получить нужную версию.
1. Выполните **`vcpkg install <library>`** .
1. Используйте **`vcpkg integrate project`** для создания пакета NuGet, который будет ссылаться на эту библиотеку для каждого конкретного проекта.

## <a name="integrate-with-visual-studio-code-linuxmacos"></a>Интеграция с Visual Studio Code (Linux и macOS)

Выполните **`vcpkg integrate install`** для настройки Visual Studio Code в Linux или macOS. Эта команда задает расположение перечисления vcpkg и включает технологию IntelliSense для исходных файлов.

## <a name="target-linux-from-windows-via-wsl"></a>Создание файлов для Linux из Windows посредством WSL

Можно создавать двоичные файлы для Linux на компьютере с Windows с помощью подсистемы Windows для Linux (WSL). Следуйте инструкциям, по [настройке WSL в Windows 10](/windows/wsl/install-win10). Затем настройте подсистему с помощью [расширения Visual Studio для Linux](https://devblogs.microsoft.com/cppblog/targeting-windows-subsystem-for-linux-from-visual-studio/). Все созданные библиотеки для Windows и Linux можно разместить в одной папке. Они доступны как в Windows, так и в WSL.

## <a name="export-compiled-binaries-and-headers"></a><a name="export_binaries_per_project"></a> Экспорт скомпилированных двоичных файлов и файлов заголовков

Требовать от каждого члена команды скачивать и компилировать библиотеки может быть неэффективно. Эту задачу способен выполнить один человек, который может использовать команду **`vcpkg export`** , чтобы собрать двоичные файлы и заголовки или пакет NuGet в один ZIP-архив. Затем он может легко предоставить его другим членам команды.

## <a name="updateupgrade-installed-libraries"></a>Обновление установленных библиотек

Общедоступный каталог регулярно пополняется новейшими версиями библиотек. Используйте **`vcpkg update`** , чтобы определить, какие из ваших локальных библиотек устарели. Когда вы будете готовы обновить свою коллекцию портов до последней версии из общедоступного каталога, выполните команду **`vcpkg upgrade`** . Она автоматически скачивает и перестраивает отдельные или все установленные библиотеки, которые устарели.

По умолчанию команда **`vcpkg upgrade`** лишь выводит список устаревших библиотек, не обновляя их. Для фактического обновления библиотек используйте параметр **`--no-dry-run`** .

```cmd
> vcpkg upgrade --no-dry-run
```

### <a name="upgrade-options"></a>Параметры обновления

- **`--no-dry-run`** : выполнение обновления; если параметр не указан, эта команда просто выводит список устаревших пакетов.
- **`--keep-going`** : продолжение установки пакетов даже при возникновении сбоя для одного из них.
- **`--triplet <t>`** : задание триады по умолчанию для неквалифицированных пакетов.
- **`--vcpkg-root <path>`** : указание каталога vcpkg для использования вместо текущего каталога или каталога средства.

### <a name="upgrade-example"></a>Пример обновления

Следующий пример показывает, как обновить только заданные библиотеки. vcpgk автоматически получает зависимости по мере необходимости.

```cmd
c:\users\satyan\vcpkg> vcpkg upgrade tiny-dnn:x86-windows zlib
The following packages are up-to-date:
   tiny-dnn:x86-windows

The following packages will be rebuilt:
    * libpng[core]:x86-windows
    * tiff[core]:x86-windows
      zlib[core]:x86-windows
Additional packages (*) will be modified to complete this operation.
If you are sure you want to rebuild the above packages, run this command with the --no-dry-run option.
```

## <a name="contribute-new-libraries"></a>Публикация новых библиотек

Вы можете включать в свою коллекцию частных портов какие угодно библиотеки. Чтобы предложить новую библиотеку для открытого каталога, откройте обращение на [странице проблем с vcpkg на сайте GitHub ](https://github.com/Microsoft/vcpkg/issues).

## <a name="remove-a-library"></a>Удаление библиотеки

Введите **`vcpkg remove`** , чтобы удалить установленную библиотеку. Если от нее зависят какие-то другие библиотеки, вам предлагается повторно выполнить команду с параметром **`--recurse`** , что приводит к удалению всех подчиненных библиотек.

## <a name="customize-vcpkg"></a>Настройка vcpkg

Вы можете изменять свой клон vcpkg как угодно. Можно даже создать несколько клонов vcpkg и изменить portfile в каждом из них. Это простой способ получить конкретные версии библиотеки или указать определенные параметры командной строки. Например, одна группа разработчиков в компании может заниматься программным обеспечением с одним набором зависимостей, а другая — с другим. Для этого необходимо настроить клон vcpkg для каждой группы. Затем следует изменить клоны так, чтобы каждый из них скачивал версии библиотек и задавал параметры компиляции в соответствии с потребностями каждой группы.

## <a name="update-vcpkg"></a>Обновление vcpkg

Диспетчер пакетов vcpkg регулярно обновляется на сайте GitHub. Чтобы обновить клон vcpkg до последней версии, в корневом каталоге vcpkg выполните команду **`git pull`** . Эта команда синхронизирует копию vcpkg с версией на сайте GitHub. После скачивания запустите начальный загрузчик еще раз. Начальный загрузчик перестраивает программу vcpkg, но оставляет установленные библиотеки на месте.

## <a name="uninstall-vcpkg"></a>Удаление vcpkg

Чтобы удалить vcpkg, просто удалите каталог vcpkg. При удалении этого каталога удаляется дистрибутив vcpkg и все библиотеки, установленные vcpkg.

## <a name="send-feedback-about-vcpkg"></a>Отправка отзыва о vcpkg

Используйте команду **`vcpkg contact --survey`** , чтобы отправить в корпорацию Майкрософт отзыв о vcpkg, включая отчеты об ошибках и предложения о функциях.

## <a name="the-vcpkg-folder-hierarchy"></a>Иерархия папок vcpkg

Все функции и данные vcpkg автономно содержатся в одной иерархии каталогов, называемой экземпляром. Никаких параметров реестра и переменных среды не используется. На вашем компьютере может быть сколько угодно экземпляров vcpkg, и они не будут конфликтовать друг с другом.

Содержимое экземпляра vcpkg

- buildtrees — содержит вложенные папки с исходными файлами, из которых строится каждая библиотека.
- docs — документация и примеры.
- downloads — кэшированные копии всех загруженных инструментов и исходных файлов. При выполнении команды установки vcpkg сначала выполняет поиск здесь.
- installed — содержит файлы заголовков и двоичные файлы для каждой установленной библиотеки. При интеграции с Visual Studio вы, по сути, указываете программе добавить эту папку в пути поиска.
- packages — внутренняя папка для промежуточного хранения между установками.
- ports — файлы, которые описывают каждую библиотеку в каталоге, ее версию и где ее можно скачать. При необходимости вы можете добавлять собственные порты.
- scripts — скрипты (CMake, PowerShell), используемые vcpkg.
- toolsrc — исходный код C++ для vcpkg и связанных компонентов.
- triplets — содержит параметры для каждой поддерживаемой целевой платформы (например, x86-windows или x64-uwp).

## <a name="command-line-reference"></a>Справочник по командной строке

|Команда|Описание|
|---------|---------|
|**`vcpkg search [pat]`**|Поиск пакетов, доступных для установки|
|**`vcpkg install <pkg>...`**|Установка пакета|
|**`vcpkg remove <pkg>...`**|Удаление пакета|
|**`vcpkg remove --outdated`**|Удаление всех устаревших пакетов|
|**`vcpkg list`**|Вывод списка установленных пакетов|
|**`vcpkg update`**|Отображение списка пакетов для обновления|
|**`vcpkg upgrade`**|Перестроение всех устаревших пакетов|
|**`vcpkg hash <file> [alg]`**|Хэширование файла с помощью конкретного алгоритма (по умолчанию SHA512)|
|**`vcpkg integrate install`**|Предоставление всем пользователям доступа к установленным пакетам. При первом использовании требуются права администратора.|
|**`vcpkg integrate remove`**|Отмена интеграции для всех пользователей|
|**`vcpkg integrate project`**|Создание пакета NuGet со ссылками для использования с конкретным проектом VS|
|**`vcpkg export <pkg>... [opt]...`**|Экспорт пакета|
|**`vcpkg edit <pkg>`**|Открытие порта для редактирования (использует %EDITOR%, по умолчанию "code")|
|**`vcpkg create <pkg> <url> [archivename]`**|Создание пакета|
|**`vcpkg cache`**|Вывод списка кэшированных скомпилированных пакетов|
|**`vcpkg version`**|Отображение сведений о версии|
|**`vcpkg contact --survey`**|Отображение контактных данных для отправки отзывов|

### <a name="options"></a>Параметры

|Параметр|Описание|
|---------|---------|
|**`--triplet <t>`**|Указание триады значений для целевой архитектуры (по умолчанию: `%VCPKG_DEFAULT_TRIPLET%`, см. также **`vcpkg help triplet`** ).|
|**`--vcpkg-root <path>`**|Указание корневого каталога vcpkg (по умолчанию: `%VCPKG_ROOT%`)|
