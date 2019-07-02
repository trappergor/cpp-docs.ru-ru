---
title: Clang/LLVM поддержку в проектах Visual Studio CMake
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++
ms.openlocfilehash: 6773d9cdb076ef305ba635306f3bc9c6575d2203
ms.sourcegitcommit: b233f05adae607f75815111006a771c432df5a9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67517109"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Clang/LLVM поддержку в проектах Visual Studio CMake

::: moniker range="<=vs-2017"

Clang поддержка доступна в Visual Studio 2019.

::: moniker-end

::: moniker range="vs-2019"

Для редактирования и отладки можно использовать Visual Studio с Clang C++ проектов CMake, целевой Windows или Linux.

**Windows**: Версия 16.1 2019 г. Visual Studio включает поддержку для редактирования, построение и отладка с помощью Clang/LLVM в проектах CMake, предназначенных для Windows. 

**Linux**: Для проектов Linux CMake специальная поддержка Visual Studio не является обязательным. Можно установить с помощью диспетчера пакетов для вашего дистрибутива Clang и добавьте соответствующие команды в файл CMakeLists.txt.

## <a name="install"></a>Установка

Поддержка по наиболее интегрированной среды разработки в Visual Studio рекомендуется использовать последнюю версию инструментов компилятора Clang для Windows. Если у вас еще нет тех, их можно установить, открыв установщик Visual Studio и выбрав **компилятора Clang для Windows** под **разработка классических приложений на C++**  дополнительные компоненты.

![Установка компонента clang](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Создать новую конфигурацию

Чтобы добавить новую конфигурацию Clang проекта CMake:

1. Щелкните правой кнопкой мыши на CMakeLists.txt в **обозревателе решений** и выберите **параметры CMake для проекта**.

1. В разделе **конфигураций**, нажмите клавишу **Добавление конфигурации** кнопки:

   ![Добавление конфигурации](media/cmake-add-config-icon.png)

1. Выберите требуемую конфигурацию Clang (Обратите внимание, что отдельные конфигурации Clang предоставляются для Windows и Linux), затем нажмите клавишу **выберите**:

   ![Конфигурация CMake Clang](media/cmake-clang-configuration.png)

1. Чтобы внести изменения в этой конфигурации, используйте **редактор параметров CMake**. Дополнительные сведения см. в разделе [сборки CMake, настроить параметры в Visual Studio](customize-cmake-settings.md).

## <a name="modify-an-existing-configuration-to-use-clang"></a>Изменить существующую конфигурацию для использования Clang

Чтобы изменить существующую конфигурацию для использования Clang, выполните следующие действия:

1. Щелкните правой кнопкой мыши на CMakeLists.txt в **обозревателе решений** и выберите **параметры CMake для проекта**.

1. В разделе **Общие** выберите **набор инструментов** раскрывающийся список и выберите нужный набор инструментов Clang:

   ![Набор инструментов CMake Clang](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Настраиваемые расположения Clang

По умолчанию Visual Studio выполняет поиск Clang в двух местах:

- (Windows) Внутренне установленная копия Clang/LLVM, входящий в состав установщика Visual Studio.
- (Windows и Linux) Переменной среды PATH.

Можно указать другое расположение, задав **CMAKE_C_COMPILER** и **CMAKE_CXX_COMPILER** переменных CMake в **параметры CMake**:

![Набор инструментов CMake Clang](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Режимы совместимости clang

Для конфигураций Windows CMake по умолчанию вызывает Clang в [clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) режим и ссылки с реализацией стандартной библиотеки. По умолчанию **clang-cl.exe** находится в `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`.

 Вы можете изменить эти значения в **параметры CMake** под **CMake переменных и кэш**. Нажмите кнопку **Показать дополнительные переменные**. Прокрутите вниз, чтобы найти **CMAKE_CXX_COMPILER**, затем нажмите кнопку **Обзор** кнопку, чтобы указать путь компилятора.

## <a name="edit-build-and-debug"></a>Изменения, построения и отладки

После настройки конфигурации Clang, можно создавать и отлаживать проект. Visual Studio обнаруживает, что при использовании компилятора Clang и предоставляет поддержку технологии IntelliSense, выделение цветом, навигации и других функций редактирования. Ошибки и предупреждения отображаются в **окно вывода**.

При отладке, можно использовать точки останова, памяти и визуализации данных и большинство функций отладки. Некоторые функции зависит от компилятора, такие как изменить и продолжить недоступны для конфигураций Clang.

![Отладка CMake Clang](media/clang-debug-visualize.png)

::: moniker-end
