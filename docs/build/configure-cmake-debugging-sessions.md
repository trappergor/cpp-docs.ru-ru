---
title: Настройка сеансов отладки CMake в Visual Studio
ms.date: 03/21/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 9899f99994935ec419fff400670644b7d78a190a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035352"
---
# <a name="configure-cmake-debugging-sessions"></a>Настройка сеансов отладки CMake

Все исполняемые целевые объекты CMake отображаются в раскрывающемся списке **Автозапускаемый элемент** на панели инструментов **Общие**. Чтобы запустить сеанс отладки, выберите один из них и запустите отладчик.

![Раскрывающийся список элементов запуска CMake](media/cmake-startup-item-dropdown.png "Раскрывающийся список элементов запуска CMake")

Можно также запустить сеанс отладки из меню CMake.

## <a name="customize-debugger-settings"></a>Настройка параметров отладчика

Чтобы настроить параметры отладчика для любого исполняемого целевого объекта CMake в проекте, щелкните правой кнопкой мыши конкретный файл CMakeLists.txt и выберите **Параметры отладки и запуска**. (Или выберите целевой объект в **представление целевых объектов** в **обозревателе решений**.) При выборе целевой объект CMake в подменю, файл с именем **launch.vs.json** создается. Он предварительно заполнен сведениями о выбранном целевом объекте CMake и позволяет указать дополнительные параметры, например аргументы программы или тип отладчика. Для ссылки на любую клавишу в **CMakeSettings.json** файл, введите перед ней с помощью `cmake.` в **launch.vs.json**. В следующем примере показано простое **launch.vs.json** файл, который запрашивает значение `remoteCopySources` в **CMakeSettings.json** файл для текущей конфигурации:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

Как только вы сохраните **launch.vs.json** файл, запись создается в **Автозапускаемый элемент** раскрывающийся список с новым именем. Путем редактирования **launch.vs.json** файл, можно создать количество конфигураций отладки, как это необходимо для любого числа целевых объектов CMake.

## <a name="support-for-cmakesettings-variables"></a>Поддержка переменных CMakeSettings

 **Launch.VS.JSON** поддерживает переменные, объявленные в **CMakeSettings.json** (см. ниже), они применяются к выбранной конфигурации. Он также имеет ключ с именем `currentDir`, который задает текущий каталог запуска приложения для локального проекта:

```json
{
  "type": "default",
  "project": "CMakeLists.txt",
  "projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

При запуске приложения значение `currentDir` имеет примерно следующий вид:

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

Ключ «cwd» задает текущий каталог для проекта удаленного запуска приложения. Значение по умолчанию — «${debugInfo.defaultWorkingDirectory}» что равняется 

```cmd
/var/tmp/src/bfc6f7f4-4f0f-8b35-80d7-9198fa973fb9/Linux-Debug
```

## <a name="see-also"></a>См. также

[Проекты CMake в Visual Studio](cmake-projects-in-visual-studio.md)<br/>
[Настройка проекта Linux CMake](../linux/cmake-linux-project.md)<br/>
[Подключение к удаленному компьютеру Linux](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Настройка параметров сборки CMake](customize-cmake-settings.md)<br/>
[Настройка сеансов отладки CMake](configure-cmake-debugging-sessions.md)<br/>
[Развертывание, запуск и отладка проекта Linux](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Справочник по предопределенной конфигурации CMake](cmake-predefined-configuration-reference.md)<br/>
