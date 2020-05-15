---
title: Поддержка Clang/LLVM в проектах Visual Studio CMake
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: 46bfe788c13df3a37dd9cba654d16cfe4c3fe177
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323178"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Поддержка Clang/LLVM в проектах Visual Studio CMake

::: moniker range="<=vs-2017"

Поддержка Clang реализована в Visual Studio версии 2019.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio с Clang можно использовать для изменения и отладки проектов C++ CMake, предназначенных для Windows или Linux.

**Windows**: Visual Studio 2019 версии 16.1 включает поддержку редактирования, сборки и отладки с помощью Clang/LLVM в проектах CMake, предназначенных для Windows.

**Linux**: Для проектов Linux CMake специальная поддержка Visual Studio не требуется. Вы можете установить Clang с помощью диспетчера пакетов вашего дистрибутива и добавить соответствующие команды в файл CMakeLists.txt.

## <a name="install"></a>Установка

Для лучшей поддержки интегрированной среды разработки в Visual Studio рекомендуется использовать новейшие средства компилятора Clang для Windows. Если они еще не установлены, их можно установить, открыв Visual Studio Installer и выбрав **Компилятор C++ Clang для Windows** в разделе дополнительных компонентов **Разработка классических приложений на C++** . При использовании настраиваемой установки Clang проверьте компонент **C++ Clang-cl для средств сборки v142**.

![Установка компонентов Clang](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Создание новой конфигурации

Чтобы добавить новую конфигурацию Clang в проект CMake, выполните следующие действия:

1. Щелкните правой кнопкой мыши файл CMakeLists.txt в **обозревателе решений** и выберите **Параметры CMake для проекта**.

1. В разделе **Конфигурации** нажмите кнопку **Добавить конфигурацию**:

   ![Добавление конфигурации](media/cmake-add-config-icon.png)

1. Выберите нужную конфигурацию Clang (обратите внимание, что для Windows и Linux предоставляются разные конфигурации Clang), а затем нажмите **Выбрать**:

   ![Конфигурация Clang для CMake](media/cmake-clang-configuration.png)

1. Чтобы внести изменения в эту конфигурацию, используйте **редактор параметров CMake**. Дополнительные сведения см. в статье [Настройка параметров сборки CMake в Visual Studio](customize-cmake-settings.md).

## <a name="modify-an-existing-configuration-to-use-clang"></a>Изменение существующей конфигурации для использования Clang

Чтобы изменить существующую конфигурацию для использования Clang, выполните следующие действия:

1. Щелкните правой кнопкой мыши файл CMakeLists.txt в **обозревателе решений** и выберите **Параметры CMake для проекта**.

1. В разделе **Общие** откройте раскрывающийся список **Набор инструментов** и выберите нужный набор инструментов Clang:

   ![Набор инструментов Clang для CMake](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Настраиваемые расположения Clang

По умолчанию Visual Studio ищет Clang в двух местах:

- (Windows) Внутренняя установленная копия Clang/LLVM, поставляемая с Visual Studio Installer.
- (Windows и Linux) Переменная среды PATH.

Можно указать другое расположение, задав переменные CMake **CMAKE_C_COMPILER** и **CMAKE_CXX_COMPILER** в **параметрах CMake**.

![Набор инструментов Clang для CMake](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Режимы совместимости Clang

Для конфигураций Windows CMake по умолчанию вызывает Clang в режиме [clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) и связывается с реализацией стандартной библиотеки Майкрософт. По умолчанию **clang-cl.exe** находится в `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`.

Эти значения можно изменить в **параметрах CMake** в разделе **Кэш и переменные CMake**. Щелкните **Показать дополнительные переменные**. Прокрутите вниз, чтобы найти **CMAKE_CXX_COMPILER**, а затем нажмите кнопку **Обзор**, чтобы указать другой путь компилятора.

## <a name="edit-build-and-debug"></a>Правка, сборка и отладка

После настройки конфигурации Clang можно выполнить сборку и отладку проекта. Visual Studio обнаруживает, что используется компилятор Clang, и предоставляет IntelliSense, выделение, навигацию и другие функции редактирования. Ошибки и предупреждения отображаются в **окне вывода**.

При отладке можно использовать точки останова, память и визуализацию данных, а также большинство других функций отладки. Некоторые зависящие от компилятора функции, такие как "Изменить и продолжить", недоступны для конфигураций Clang.

![Отладка Clang в CMake](media/clang-debug-visualize.png)

::: moniker-end
