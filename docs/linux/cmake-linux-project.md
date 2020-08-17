---
title: Создание проекта CMake для Linux в Visual Studio
description: Как создать проект CMake для Linux в Visual Studio
ms.date: 08/06/2020
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 1b622bcd2af49ee51f7546be4c7a6d804c3102d0
ms.sourcegitcommit: 2034f8e744a8b36cff8b15e9a5cfe684afebadfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "88043828"
---
# <a name="create-a-cmake-linux-project-in-visual-studio"></a>Создание проекта CMake для Linux в Visual Studio

::: moniker range="vs-2015"
Поддержка Linux реализована в Visual Studio версии 2017 и выше. Чтобы увидеть документацию для этих версий, установите в расположенном над содержанием раскрывающемся списке **Версия** пункт **Visual Studio 2017** или **Visual Studio 2019**.
::: moniker-end

::: moniker range=">=vs-2017"

Рекомендуется использовать CMake для проектов, которые являются кроссплатформенными или будут создаваться с открытым кодом. Проекты CMake можно использовать для сборки и отладки одного и того же исходного кода в Windows, подсистеме Windows для Linux (WSL) и удаленных системах.

## <a name="before-you-begin"></a>Перед началом

Сначала убедитесь, что вы установили рабочую нагрузку Visual Studio для Linux, включая компонент CMake. Она является рабочей нагрузкой **Разработка для Linux на C++** в Visual Studio Installer. Если вы не уверены в том, что она установлена, см. статью [Загрузка, установка и настройка рабочей нагрузки Linux](download-install-and-setup-the-linux-development-workload.md).

Также убедитесь, что на удаленном компьютере установлены следующие компоненты:

- gcc
- gdb
- rsync
- zip
- ninja-build (Visual Studio 2019 или более поздней версии)
::: moniker-end

::: moniker range="vs-2017"
Для поддержки CMake в Visual Studio требуется поддержка режима сервера, введенная в CMake 3.8. Для версии CMake от Майкрософт скачайте последние готовые двоичные файлы по адресу [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

Двоичные файлы устанавливаются в каталог `~/.vs/cmake`. После развертывания двоичных файлов автоматически выполняется повторное создание проекта. Если файл CMake, указанный в поле `cmakeExecutable` в *CMakeSettings.json*, является недопустимым (файл не существует или версия файла не поддерживается), то при наличии предварительно созданных двоичных файлов Visual Studio игнорирует поле `cmakeExecutable` и использует эти предварительно созданные двоичные файлы.

Visual Studio 2017 не может создать проект CMake с нуля, но можно открыть папку, содержащую имеющийся проект CMake, как описано в следующем разделе.
::: moniker-end

::: moniker range=">=vs-2019"
Visual Studio 2019 можно использовать для сборки и отладки в удаленной системе Linux или WSL, и в этой системе будет вызываться CMake. На целевом компьютере должен быть установлен Cmake версии 3.14 или более поздней.

Убедитесь, что на целевом компьютере установлена последняя версия CMake. Часто в дистрибутиве версия, которую предлагает диспетчер пакетов по умолчанию, не является актуальной и не поддерживает все функции, необходимые для работы с Visual Studio. Visual Studio 2019 определяет, установлена ли последняя версия CMake в системе Linux. Если такая версия не найдена, Visual Studio отображает информационную панель в верхней части области редактора. В ней предлагается установить CMake из [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases).

С помощью Visual Studio 2019 можно создать проект CMake с нуля или открыть имеющийся. Чтобы создать проект CMake, следуйте приведенным ниже инструкциям. Или перейдите к разделу [Открытие папки проекта CMake](#open-a-cmake-project-folder), если у вас уже есть проект CMake.

## <a name="create-a-new-linux-cmake-project"></a>Создание нового проекта CMake в Linux

Чтобы создать проект Linux CMake в Visual Studio 2019, сделайте следующее:

1. Выберите **Файл > Создать проект** в меню Visual Studio или нажмите клавиши **Ctrl + Shift + N**.
1. Задайте для параметра **Язык** значение **C++** и выполните поиск по строке CMake. Теперь щелкните **Далее**. Укажите **имя** и **расположение**, а затем щелкните **Создать**.

Кроме того, можно открыть собственный проект CMake в Visual Studio 2019. Подробные сведения см. в следующем разделе.

Visual Studio создает минимальный файл *CMakeLists.txt*, в котором содержится только имя исполняемого файла и минимальная требуемая версия CMake. При необходимости вы можете вручную изменить этот файл. Visual Studio никогда не переопределяет пользовательские изменения.

Чтобы получить представление об изменении и создании сценариев CMake в Visual Studio 2019, ознакомьтесь со следующими материалами:

- [Внутренняя документация в Visual Studio для CMake](https://devblogs.microsoft.com/cppblog/in-editor-documentation-for-cmake-in-visual-studio/)
- [Навигация по коду для сценариев CMake](https://devblogs.microsoft.com/cppblog/code-navigation-for-cmake-scripts/)
- [Простое добавление, удаление и переименование файлов и целевых объектов в проектах CMake](https://devblogs.microsoft.com/cppblog/easily-add-remove-and-rename-files-and-targets-in-cmake-projects/)
::: moniker-end

::: moniker range=">=vs-2017"
## <a name="open-a-cmake-project-folder"></a>Открытие папки проекта CMake

Когда вы открываете папку, содержащую существующий проект CMake, Visual Studio автоматически настраивает IntelliSense и сборки, используя переменные в кэше CMake. Локальные параметры конфигурации и отладки хранятся в файлах JSON. При желании вы можете предоставить доступ к этим файлам другим пользователям Visual Studio.

Visual Studio не изменяет файлы *CMakeLists.txt*. Это позволяет вашим коллегам, работающим над тем же проектом, продолжать использовать имеющиеся инструменты. После того как вы сохраните изменения в файле *CMakeLists.txt* и (в некоторых случаях) в файле *CMakeSettings.json*, Visual Studio повторно создает кэш. Если вы используете конфигурацию **Существующий кэш**, то Visual Studio не изменяет содержимое кэша.

Общие сведения о поддержке CMake в Visual Studio см. в статье о [проектах CMake в Visual Studio](../build/cmake-projects-in-visual-studio.md). Прочитайте статью, прежде чем продолжить чтение этого раздела.

Чтобы приступить к работе, в главном меню последовательно выберите пункты **Файл** > **Открыть** > **Папка** или введите `devenv.exe <foldername>` в окне [командной строки разработчика](../build/building-on-the-command-line.md). В открываемой паке должен находиться файл *CMakeLists.txt* вместе с исходным кодом.

Ниже приведен пример простого файла *CMakeLists.txt* и CPP-файла.

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

*CMakeLists.txt*:

```txt
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="next-steps"></a>Дальнейшие действия

[Настройка проекта Linux CMake](cmake-linux-configure.md)

## <a name="see-also"></a>См. также

[Проекты CMake в Visual Studio](../build/cmake-projects-in-visual-studio.md)<br/>
::: moniker-end
