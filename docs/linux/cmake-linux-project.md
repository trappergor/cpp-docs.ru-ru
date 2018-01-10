---
title: "Настройка проекта Linux CMake в Visual Studio | Документы Майкрософт"
ms.custom: 
ms.date: 10/25/2107
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 67665f3271caf71d16788b2e102d0e756d9f702f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="configure-a-linux-cmake-project"></a>Настройка проекта Linux CMake
  
**Visual Studio 2017 версия 15.4** При установке рабочей нагрузки Linux C++ по умолчанию выбирается поддержка CMake для Linux. Теперь вы можете работать с существующей базой кода, где CMake не требуется преобразовывать в проект VS. Если база кода является кроссплатформенной, в Visual Studio можно создавать решения как для Windows, так и для Linux. 

В этом разделе предполагается, что вы уже знакомы с поддержкой CMake в Visual Studio. Дополнительные сведения см. в разделе [Инструменты CMake для Visual C++](../ide/cmake-tools-for-visual-cpp.md). Дополнительные сведения о CMake см. на странице [Сборка, тестирование и упаковка программного обеспечения с помощью CMake](https://cmake.org/).

> [!NOTE] 
> Для поддержки CMake в Visual Studio требуется поддержка режима сервера, которая была введена в CMake 3.8. Если диспетчер пакетов предоставляет более старую версию CMake, можно воспользоваться обходным решением и создать CMake 3.8 из источника.



## <a name="open-a-folder"></a>Открытие папки
Чтобы приступить к работе, в основном меню выберите **Файл | Открыть | Папка** или введите `devenv.exe <foldername>` в командной строке. В открываемой паке должен находиться файл CMakeLists.txt вместе с исходным кодом.
Ниже приведен пример простого файла CMakeLists.txt и CPP-файла.

```cpp
// Hello.cpp

#include <iostream>;
 
int main(int argc, char* argv[])
{
    std::cout << "Hello" << std::endl;
}
```

CMakeLists.txt: 
```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Выбор целевого объекта Linux
После открытия папки Visual Studio выполняет синтаксический анализ файла CMakeLists.txt и задает целевой объект Windows x86-Debug. Чтобы изменить платформу на Linux, измените параметры проекта на Linux-Debug или Linux-Release.

По умолчанию Visual Studio выбирает первую удаленную систему в списке (в разделе **Инструменты | Параметры | Межплатформенные | Диспетчер подключений**). Если удаленные подключения не найдены, вам будет предложено создать нужное.

После указания целевого объекта Linux источник копируется на компьютер Linux. Затем CMake выполняется на компьютере Linux, чтобы создать кэш CMake для проекта.  

![Создание кэша CMake в Linux](media/cmake-linux-1.png "Создание кэша CMake в Linux")  

## <a name="debug-the-project"></a>Отладка проекта  
Чтобы отладить код в удаленной системе, задайте точку останова, выберите целевой объект CMake в качестве элемента автозагрузки на панели инструментов рядом с параметром проекта и нажмите кнопку выполнения (или нажмите клавишу F5).

## <a name="configure-cmake-settings-for-linux"></a>Настройка параметров CMake для Linux
Чтобы изменить параметры CMake по умолчанию, в основном меню выберите **CMake | Изменить параметры CMake | CMakeLists.txt** либо щелкните правой кнопкой мыши файл CMakeSettings.txt в **обозревателе решений** и выберите **Изменить параметры CMake**. Visual Studio создаст новый файл в папке с именем `CMakeSettings.json`, который заполняется конфигурациями по умолчанию, перечисленными в пункте меню параметров проекта. Ниже приведен пример конфигурации по умолчанию для Linux-Debug на основании предыдущего примера кода.

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```
Значение `name` может быть любым. Значение `remoteMachineName` указывает, какая удаленная система будет целевым объектом, если систем несколько. Чтобы помочь вам выбрать нужную систему, для этого поля включена технология IntelliSense. Поле `remoteCMakeListsRoot` указывает, в какое место в удаленной системе будут скопированы источники проекта Поле `remoteBuildRoot` указывает, в каком месте в удаленной системе будут формироваться выходные данные сборки. Эти выходные данные также копируются локально в место, указанное с помощью `buildRoot`.

## <a name="building-a-supported-cmake-release-from-source"></a>Сборка поддерживаемого выпуска CMake из источника
Минимальной версией CMake, необходимой на компьютере Linux, является 3.8. Кроме того, должен поддерживаться режим сервера. Чтобы проверить это, выполните следующую команду:

```cmd
cmake --version
```

Чтобы проверить, включен ли режим сервера, выполните следующую команду:

```cmd
cmake -E capabilities
```

В выходных данных проверьте, что "serverMode":true. Обратите внимание, что даже при компиляции CMake из источника, как описано ниже, после завершения процесса необходимо проверить возможности. Система Linux может накладывать ограничения, которые препятствуют включению режима сервера.

Чтобы начать сборку из источника в оболочке системы Linux, убедитесь, что диспетчер пакетов обновлен и вам доступны cmake и git. Сначала клонируйте источники CMake:

```cmd
sudo apt-get update
sudo apt-get install -y git cmake
git clone https://github.com/Kitware/CMake.git
cd CMake
```

Затем убедитесь, что используется поддерживаемый выпуск CMake для Visual Studio. Мы активно отслеживаем разработки CMake, но не можем гарантировать, что поддерживаются последние версии. Чтобы создать CMake 3.9.0 (например), сначала выполните:

```cmd
git checkout tags/v3.9.0
```

Затем выполните следующие команды:

```cmd
mkdir out
cd out
cmake ../
make
sudo make install
```

Приведенные выше команды позволяют построить и установить текущий выпуск CMake в каталог /usr/local/bin. Выполните следующую команду, чтобы проверить, что используется версия 3.8 или более поздняя и включен режим сервера:

```cmd
/usr/local/bin/cmake –version
cmake -E capabilities
```

## <a name="see-also"></a>См. также
[Работа со свойствами проектов](../ide/working-with-project-properties.md)  
[Инструменты CMake для Visual C++](../ide/cmake-tools-for-visual-cpp.md)