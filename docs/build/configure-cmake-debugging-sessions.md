---
title: Настройка сеансов отладки CMake в Visual Studio
ms.date: 03/21/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 41f53c0c3ea46a8a1aa11215968aaee6c13c2dea
ms.sourcegitcommit: e33126222c418daf977533ea9e2819d99e0d7b8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72534105"
---
# <a name="configure-cmake-debugging-sessions"></a>Настройка сеансов отладки CMake

Все исполняемые целевые объекты CMake отображаются в раскрывающемся списке **Автозапускаемый элемент** на панели инструментов **Общие**. Чтобы запустить сеанс отладки, выберите один из них и запустите отладчик.

![Раскрывающийся список элементов автозагрузки](media/cmake-startup-item-dropdown.png "Раскрывающийся список элементов автозагрузки")

Можно также запустить сеанс отладки из обозреватель решений. Сначала перейдите в **представление "целевые объекты CMAK** " в окне **Обозреватель решений** .

![Кнопка просмотра целевых объектов CMak](media/cmake-targets-view.png  "Пункт меню "Просмотр целевых объектов CMak"")

Затем щелкните правой кнопкой мыши любой исполняемый файл и выберите **Отладка** или **Отладка и параметры запуска**. **Отладка** автоматически начинает отладку выбранного целевого объекта на основе активной конфигурации. **Параметры отладки и запуска** открывает файл *Launch. vs. JSON* и добавляет новую конфигурацию отладки для выбранного целевого объекта.

## <a name="customize-debugger-settings"></a>Настройка параметров отладчика

Чтобы настроить параметры отладчика для любого исполняемого целевого объекта CMake в проекте, щелкните правой кнопкой мыши конкретный файл CMakeLists.txt и выберите **Параметры отладки и запуска**. (Или выберите целевой объект в **представлении "целевые объекты** " в **Обозреватель решений**.) При выборе целевого объекта CMak в подменю создается файл **Launch. vs. JSON** . Он предварительно заполнен сведениями о выбранном целевом объекте CMake и позволяет указать дополнительные параметры, например аргументы программы или тип отладчика. Чтобы сослаться на любой ключ в файле **CMakeSettings. JSON** , добавьте его в `cmake.` **Launch. vs. JSON**. В следующем примере показан простой файл **Launch. vs. JSON** , который извлекает значение ключа `remoteCopySources` в файле **CMakeSettings. JSON** для текущей выбранной конфигурации:

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

После сохранения файла **Launch. vs. JSON** в раскрывающемся списке **автозагружаемый элемент** создается запись с новым именем. Изменяя файл **Launch. vs. JSON** , можно создать столько конфигураций отладки, сколько вам нравится для любого количества целевых объектов CMAK.

## <a name="support-for-cmakesettings-variables"></a>Поддержка переменных CMakeSettings

 **Launch. vs. JSON** поддерживает переменные, объявленные в **CMakeSettings. JSON** (см. ниже) и применимые к текущей конфигурации. Он также имеет ключ с именем `currentDir`, который задает текущий каталог запуска приложения для локального проекта:

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

Ключ "КВД" задает текущий каталог запуска приложения для удаленного проекта. Значение по умолчанию — "$ {Дебугинфо. defaultWorkingDirectory}", результатом которого является 

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
