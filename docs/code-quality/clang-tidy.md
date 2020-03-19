---
title: Использование Clang в Visual Studio
description: Как использовать Clang в Visual Studio для анализа кода Майкрософт C++ .
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
author: frozenpandaman
ms.author: efessler
ms.openlocfilehash: 3dbe66e9d7117c027c0ec867011189824c59ce31
ms.sourcegitcommit: 21e168731b8fe0eaff18f070cee5d54aa5782c2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "79469899"
---
# <a name="using-clang-tidy-in-visual-studio"></a>Использование Clang в Visual Studio

::: moniker range="<=vs-2017"

Для поддержки Clang требуется Visual Studio 2019 версии 16,4 или более поздней. Чтобы просмотреть документацию, выберите Visual Studio 2019 в селекторе версии документации.

::: moniker-end

::: moniker range=">=vs-2019"

Анализ кода изначально поддерживает Clang для проектов MSBuild и CMak независимо [от](https://clang.llvm.org/extra/clang-tidy/) того, используются ли наборы инструментов CLANG или компилятором MSVC. Clangные проверки могут выполняться как часть анализа фонового кода. Они отображаются в виде предупреждений в редакторе (волнистых линий) и отображаются в Список ошибок.

Clang поддержка по включению доступна начиная с Visual Studio 2019 версии 16,4. Он включается автоматически при выборе C++ рабочей нагрузки в Visual Studio Installer.

Clang — это средство анализа по умолчанию при использовании набора инструментов LLVM/Clang-CL, доступных как в MSBuild, так и в CMak. Его можно настроить при использовании набора инструментов КОМПИЛЯТОРОМ MSVC для выполнения параллельно или для замены стандартного анализа кода. При использовании набора инструментов Clang-CL анализ кода Microsoft недоступен.

Clang выполняется после успешной компиляции. Чтобы получить результаты Clang, может потребоваться устранить ошибки исходного кода.

## <a name="msbuild"></a>MSBuild

Вы можете настроить Clang для запуска как часть анализа кода и выполнять сборку на странице " **анализ кода** > **общие** " в окно свойств проекта. Параметры для настройки средства можно найти в подменю Clang.

Дополнительные сведения см. [в разделе инструкции. Установка свойств анализа кода для C/C++ Projects](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md).

## <a name="cmake"></a>CMake

В проектах CMak можно настроить Clang проверки в пределах `CMakeSettings.json`. После открытия щелкните "изменить JSON" в правом верхнем углу редактора параметров проекта CMak. Распознаются следующие ключи:

- `enableMicrosoftCodeAnalysis`: включает анализ кода Майкрософт
- `enableClangTidyCodeAnalysis`: включает анализ Clangности
- `clangTidyChecks`: конфигурация, Clang, указанная в виде списка с разделителями-запятыми, то есть включает или отключает

Если не указано ни одного из параметров "включить", Visual Studio выберет средство анализа, соответствующее используемому набору инструментов платформы.

## <a name="warning-display"></a>Отображение предупреждений

Clangные запуски приводят к отображению предупреждений в Список ошибок, а также как волнистые части в редакторе в соответствующих разделах кода. Используйте столбец Category (категория) в Список ошибок для сортировки и упорядочения предупреждений Clang. Можно настроить предупреждения в редакторе, установив параметр "отключить неподчеркнутые коды анализа кода" в меню " **сервис** > **Параметры**".

## <a name="clang-tidy-configuration"></a>Конфигурация с Clang

Можно настроить проверки, выполняемые Clang в Visual Studio с помощью параметра **Clang-configure checks** . Эти входные данные предоставляются в аргументе **--checks** средства. Любую дальнейшую настройку можно добавить в пользовательские файлы *`.clang-tidy`* . Дополнительные сведения см. в [Clang документации по LLVM.org](https://clang.llvm.org/extra/clang-tidy/).

## <a name="see-also"></a>См. также раздел

- [Поддержка Clang/LLVM для проектов MSBuild](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [Поддержка Clang/LLVM для проектов CMak](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end
