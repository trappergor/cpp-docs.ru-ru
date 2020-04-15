---
title: Поддержка Clang/LLVM в проектах Visual Studio CMake
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: 46bfe788c13df3a37dd9cba654d16cfe4c3fe177
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323178"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Поддержка Clang/LLVM в проектах Visual Studio CMake

::: moniker range="<=vs-2017"

Clang поддержка доступна в Visual Studio 2019.

::: moniker-end

::: moniker range="vs-2019"

Вы можете использовать Visual Studio с Clang для отсеивательных и отладить проекты C'CMake, ориентированные на Windows или Linux.

**Windows**: Visual Studio 2019 версия 16.1 включает в себя поддержку редактирования, создания и отладки с Clang / LLVM в проектах CMake, ориентированных на Windows.

**Linux**: Для linux CMake проектов, специальная поддержка Visual Studio не требуется. Вы можете установить Clang с помощью менеджера пакетов дистро и добавить соответствующие команды в файл CMakeLists.txt.

## <a name="install"></a>Установка

Для лучшей поддержки IDE в Visual Studio мы рекомендуем использовать новейшие инструменты компилятора Clang для Windows. Если у вас их еще нет, вы можете установить их, открыв установку Visual Studio и выбрав **компилятор C' Clang для Windows** в **разработке рабочего стола с** дополнительными компонентами C'. При использовании пользовательской установки Clang проверьте компонент **инструментов сборки c's Clang-cl на v142.**

![Установка компонента ляга](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Создание новой конфигурации

Чтобы добавить новую конфигурацию Clang в проект CMake:

1. Нажмите на CMakeLists.txt в **Solution Explorer** и выберите **настройки CMake для проекта.**

1. В **настройках**нажмите кнопку **«Добавить конфигурацию»:**

   ![Добавление конфигурации](media/cmake-add-config-icon.png)

1. Выберите нужную конфигурацию Clang (обратите внимание, что отдельные конфигурации Clang предусмотрены для Windows и Linux), затем нажмите **Выберите:**

   ![Конфигурация CMake Clang](media/cmake-clang-configuration.png)

1. Чтобы внести изменения в эту конфигурацию, используйте **редактор настроек CMake.** Для получения дополнительной информации смотрите [настройки CMake построить настройки в Visual Studio](customize-cmake-settings.md).

## <a name="modify-an-existing-configuration-to-use-clang"></a>Изменение существующей конфигурации для использования Clang

Чтобы изменить существующую конфигурацию для использования Clang, выполните следующие действия:

1. Нажмите на CMakeLists.txt в **Solution Explorer** и выберите **настройки CMake для проекта.**

1. Под **General** выберите отбрасывание **наборов инструментов Toolset** и выберите нужный набор инструментов Clang:

   ![Набор инструментов CMake Clang](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Пользовательские места clang

По умолчанию Visual Studio ищет Clang в двух местах:

- (Окна) Внутренне установленная копия Clang/LLVM, которая поставляется с установщиком Visual Studio.
- (Windows и Linux) Переменная среды PATH.

Вы можете указать другое место, установив переменные **CMAKE_C_COMPILER** и **CMAKE_CXX_COMPILER** CMake в **настройках CMake:**

![Набор инструментов CMake Clang](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Режимы совместимости Clang

Для конфигураций Windows CMake по умолчанию вызывает Clang в режиме [лягш-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) и ссылки на реализацию Стандартной библиотеки Microsoft. По умолчанию, **clang-cl.exe** находится в `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`.

Эти значения можно изменить в **настройках CMake** под **переменными CMake и кэшом.** Нажмите **Показать расширенные переменные**. Прокрутите вниз, чтобы найти **CMAKE_CXX_COMPILER,** затем нажмите кнопку **«Просмотр»,** чтобы указать другой путь компилятора.

## <a name="edit-build-and-debug"></a>Отсечение, сборка и отладка

После настройки конфигурации Clang можно создать и отладить проект. Visual Studio обнаруживает, что вы используете компилятор Clang, и предоставляет функции IntelliSense, выделения, навигации и других функций редактирования. Ошибки и предупреждения отображаются в **окне вывода.**

При отладке можно использовать точки разрыва, визуализацию памяти и данных, а также большинство других функций отладки. Некоторые функции, зависящие от компилятора, такие как Edit и Continue, недоступны для конфигураций Clang.

![Отладка CMake Clang](media/clang-debug-visualize.png)

::: moniker-end
