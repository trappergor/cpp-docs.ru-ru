---
title: Поддержка Clang/LLVM в проектах Visual Studio CMak
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: a71f9dc98f74247788558d1b7dccf3e117f43072
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2020
ms.locfileid: "77416026"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Поддержка Clang/LLVM в проектах Visual Studio CMak

::: moniker range="<=vs-2017"

Поддержка Clang доступна в Visual Studio 2019.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio с Clang можно использовать для изменения и отладки C++ проектов CMAK, предназначенных для Windows или Linux.

**Windows**: Visual Studio 2019 версии 16,1 включает поддержку редактирования, сборки и отладки с помощью CLANG/LLVM в проектах CMAK, предназначенных для Windows.

**Linux**: для проектов Linux CMAK не требуется специальная поддержка Visual Studio. Вы можете установить Clang с помощью диспетчера пакетов дистрибутив и добавить соответствующие команды в файл CMakeLists. txt.

## <a name="install"></a>Установка

Для лучшей поддержки интегрированной среды разработки в Visual Studio рекомендуется использовать новейшие средства компилятора Clang для Windows. Если они еще не установлены, их можно установить, открыв Visual Studio Installer и выбрав  **C++ компилятор Clang для Windows** в разделе **Разработка настольных C++ приложений с** дополнительными компонентами. При использовании пользовательской установки Clang проверьте компонент  **C++ Clang-CL для v142 Build Tools** .

![Установка компонента Clang](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Создание новой конфигурации

Чтобы добавить новую конфигурацию Clang в проект CMak, выполните следующие действия.

1. Щелкните правой кнопкой мыши CMakeLists. txt в **Обозреватель решений** и выберите **Параметры CMAK для проекта**.

1. В разделе **конфигурации**нажмите кнопку **Добавить конфигурацию** :

   ![Добавить конфигурацию](media/cmake-add-config-icon.png)

1. Выберите нужную конфигурацию Clang (Обратите внимание, что для Windows и Linux предоставляются отдельные конфигурации Clang), а затем нажмите кнопку **выбрать**.

   ![Конфигурация Clang для CMak](media/cmake-clang-configuration.png)

1. Чтобы внести изменения в эту конфигурацию, используйте **Редактор параметров CMAK**. Дополнительные сведения см. [в разделе Настройка параметров сборки CMAK в Visual Studio](customize-cmake-settings.md).

## <a name="modify-an-existing-configuration-to-use-clang"></a>Изменение существующей конфигурации для использования Clang

Чтобы изменить существующую конфигурацию для использования Clang, выполните следующие действия.

1. Щелкните правой кнопкой мыши CMakeLists. txt в **Обозреватель решений** и выберите **Параметры CMAK для проекта**.

1. В разделе **Общие** выберите раскрывающийся список **набор инструментов** и выберите нужный набор инструментов Clang:

   ![Набор средств Clang для CMak](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Настраиваемые расположения Clang

По умолчанию Visual Studio ищет Clang в двух местах:

- Windows Внутренняя установленная копия Clang/LLVM, поставляемая с установщиком Visual Studio.
- (Windows и Linux) Переменная среды PATH.

Можно указать другое расположение, задав переменные **CMAKE_C_COMPILER** и **CMAKE_CXX_COMPILER** CMAK в **параметрах CMAK**:

![Набор средств Clang для CMak](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Режимы совместимости Clang

Для конфигураций Windows Пакет адменистрирования диспетчера подключений (CMak) по умолчанию вызывает Clang в режиме [Clang-CL](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) и ссылается на реализацию Microsoft стандартной библиотеки. По умолчанию **Кланг-кл. exe** находится в `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`.

Эти значения можно изменить в **параметрах CMAK** в разделе **переменные и кэш CMAK**. Щелкните **Показывать дополнительные переменные**. Прокрутите вниз, чтобы найти **CMAKE_CXX_COMPILER**, а затем нажмите кнопку **обзора** , чтобы указать другой путь компилятора.

## <a name="edit-build-and-debug"></a>Изменение, сборка и отладка

После настройки конфигурации Clang можно выполнить сборку и отладку проекта. Visual Studio обнаруживает, что используется компилятор Clang и обеспечивает IntelliSense, выделение, навигацию и другие функции редактирования. Ошибки и предупреждения отображаются в **окно вывода**.

При отладке можно использовать точки останова, память и визуализацию данных, а также большинство других функций отладки. Некоторые зависящие от компилятора функции, такие как "изменить и продолжить", недоступны для конфигураций Clang.

![Отладка Clang в CMak](media/clang-debug-visualize.png)

::: moniker-end
