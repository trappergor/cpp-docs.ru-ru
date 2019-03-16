---
title: Настройка сеансов отладки CMake в Visual Studio
ms.date: 03/05/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 9a4dd009544a4590c336697ba2162eec45718869
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827926"
---
# <a name="configure-cmake-debugging-sessions"></a>Настройка сеансов отладки CMake

Все исполняемые целевые объекты CMake отображаются в раскрывающемся списке **Автозапускаемый элемент** на панели инструментов **Общие**. Чтобы запустить сеанс отладки, выберите один из них и запустите отладчик.

![Раскрывающийся список элементов запуска CMake](media/cmake-startup-item-dropdown.png "Раскрывающийся список элементов запуска CMake")

Можно также запустить сеанс отладки из меню CMake.

## <a name="customize-debugger-settings"></a>Настройка параметров отладчика

Чтобы настроить параметры отладчика для любого исполняемого целевого объекта CMake в проекте, щелкните правой кнопкой мыши конкретный файл CMakeLists.txt и выберите **Параметры отладки и запуска**. При выборе целевого объекта CMake в подменю создается файл `launch.vs.json`. Он предварительно заполнен сведениями о выбранном целевом объекте CMake и позволяет указать дополнительные параметры, например аргументы программы или тип отладчика. Чтобы сослаться на любой ключ в файле `CMakeSettings.json`, поставьте перед ним `cmake.` в `launch.vs.json`. В следующем примере показан простой файл `launch.vs.json`, получающий значение ключа `remoteCopySources` в файле `CMakeSettings.json` для текущей конфигурации:

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

Сразу после сохранения файла `launch.vs.json` в раскрывающемся списке **Элемент запуска** создается запись с новым именем. Изменяя файл `launch.vs.json`, можно создать сколько угодно конфигураций отладки для любого числа целевых объектов CMake.

## <a name="support-for-cmakesettings-variables"></a>Поддержка переменных CMakeSettings

 `Launch.vs.json` поддерживает переменные, объявляемые в `CMakeSettings.json` (см. ниже) и применяемые к выбранной конфигурации. Он также содержит ключ `currentDir`, задающий текущий каталог запускаемого приложения:

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
## <a name="see-also"></a>См. также

[Проекты CMake в Visual Studio](cmake-projects-in-visual-studio.md)<br/>
[Настройка проекта Linux CMake](../linux/cmake-linux-project.md)<br/>
[Подключение к удаленному компьютеру Linux](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Настройка параметров сборки CMake](customize-cmake-settings.md)<br/>
[Настройка сеансов отладки CMake](configure-cmake-debugging-sessions.md)<br/>
[Развертывание, запуск и отладка проекта Linux](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Справочник по предопределенной конфигурации CMake](cmake-predefined-configuration-reference.md)<br/>