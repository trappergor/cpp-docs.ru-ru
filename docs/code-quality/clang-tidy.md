---
title: Использование Clang в Visual Studio
description: Как использовать Clang в Visual Studio для анализа кода Microsoft C++.
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
ms.openlocfilehash: 30378ab0713d5e00e704f778646b9d60856f2234
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842472"
---
# <a name="using-clang-tidy-in-visual-studio"></a>Использование Clang в Visual Studio

::: moniker range="<=vs-2017"

Для поддержки Clang требуется Visual Studio 2019 версии 16,4 или более поздней. Чтобы отобразилась документация для этой версии, установите в этой статье селектор **Версия** Visual Studio в положение "Visual Studio 2019". Он находится в верхней части оглавления на этой странице.

::: moniker-end

::: moniker range=">=vs-2019"

Анализ кода изначально поддерживает Clang для проектов MSBuild и CMak независимо [от](https://clang.llvm.org/extra/clang-tidy/) того, используются ли наборы инструментов CLANG или компилятором MSVC. Clangные проверки могут выполняться как часть анализа фонового кода. Они отображаются в виде предупреждений в редакторе (волнистых линий) и отображаются в Список ошибок.

Clang поддержка по включению доступна начиная с Visual Studio 2019 версии 16,4. Он включается автоматически при выборе рабочей нагрузки C++ в Visual Studio Installer.

Clang — это средство анализа по умолчанию при использовании набора инструментов LLVM/Clang-CL, доступных как в MSBuild, так и в CMak. Его можно настроить при использовании набора инструментов КОМПИЛЯТОРОМ MSVC для выполнения параллельно или для замены стандартного анализа кода. При использовании набора инструментов Clang-CL анализ кода Microsoft недоступен.

Clang выполняется после успешной компиляции. Чтобы получить результаты Clang, может потребоваться устранить ошибки исходного кода.

## <a name="msbuild"></a>MSBuild

Clang можно настроить для выполнения как части анализа кода и построения на странице " **анализ кода**  >  **Общие** " в проекте окно свойств. Параметры для настройки средства можно найти в подменю Clang.

Дополнительные сведения см. [в разделе инструкции. Установка свойств анализа кода для проектов C/C++](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md).

## <a name="cmake"></a>CMake

В проектах CMak можно настроить Clang проверки в `CMakeSettings.json` . После открытия выберите "изменить JSON" в правом верхнем углу редактора параметров проекта CMak. Распознаются следующие ключи:

- `enableMicrosoftCodeAnalysis`: Включает анализ кода Майкрософт
- `enableClangTidyCodeAnalysis`: Включает анализ Clangности
- `clangTidyChecks`: Clang конфигурация, указанная в виде списка с разделителями-запятыми, то есть включенных или отключенных

Если не указано ни одного из параметров "включить", Visual Studio выберет средство анализа, соответствующее используемому набору инструментов платформы.

## <a name="warning-display"></a>Отображение предупреждений

Clangные запуски приводят к отображению предупреждений в Список ошибок, а также как волнистые части в редакторе в соответствующих разделах кода. Используйте столбец Category (категория) в Список ошибок для сортировки и упорядочения предупреждений Clang. Можно настроить предупреждения в редакторе, установив параметр "отключить неподчеркнутые коды анализа кода" в разделе **Сервис**  >  **Параметры**.

## <a name="clang-tidy-configuration"></a>Конфигурация с Clang

Можно настроить проверки, выполняемые Clang в Visual Studio с помощью параметра **Clang-configure checks** . Эти входные данные предоставляются **`--checks`** аргументу средства. Любую дальнейшую настройку можно добавить в пользовательские *`.clang-tidy`* файлы. Дополнительные сведения см. в [Clang документации по LLVM.org](https://clang.llvm.org/extra/clang-tidy/).

## <a name="see-also"></a>См. также раздел

- [Поддержка Clang/LLVM для проектов MSBuild](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [Поддержка Clang/LLVM для проектов CMak](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end
