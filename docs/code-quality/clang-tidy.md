---
title: Использование Clang-Tidy в Visual Studio
description: Использование Clang-Tidy в Visual Studio для анализа кода Microsoft C++.
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
ms.openlocfilehash: 5b2da222caea435bdb24d774b5e93c995e734bb7
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919076"
---
# <a name="using-clang-tidy-in-visual-studio"></a>Использование Clang-Tidy в Visual Studio

::: moniker range="<=msvc-150"

Для поддержки Clang-Tidy требуется Visual Studio 2019 версии 16,4 или более поздней. Чтобы отобразилась документация для этой версии, установите в этой статье селектор **Версия** Visual Studio в положение "Visual Studio 2019". Он находится в верхней части оглавления на этой странице.

::: moniker-end

::: moniker range=">=msvc-160"

Анализ кода изначально поддерживает Clang для проектов MSBuild и CMak независимо [от](https://clang.llvm.org/extra/clang-tidy/) того, используются ли наборы инструментов CLANG или компилятором MSVC. Проверки Clang-Tidy могут выполняться как часть анализа фонового кода. Они отображаются в виде предупреждений в редакторе (волнистых линий) и отображаются в Список ошибок.

Поддержка Clang-Tidy доступна начиная с Visual Studio 2019 версии 16,4. Он включается автоматически при выборе рабочей нагрузки C++ в Visual Studio Installer.

Clang-Tidy является средством анализа по умолчанию при использовании набора инструментов LLVM/Clang-CL, доступных как в MSBuild, так и в CMak. Его можно настроить при использовании набора инструментов КОМПИЛЯТОРОМ MSVC для выполнения параллельно или для замены стандартного анализа кода. При использовании набора инструментов Clang-CL анализ кода Microsoft недоступен.

Clang-Tidy запускается после успешной компиляции. Чтобы получить Clang-Tidy результаты, может потребоваться устранить ошибки исходного кода.

## <a name="msbuild"></a>MSBuild

Вы можете настроить Clang-Tidy для запуска как части анализа кода и построения на странице " **анализ кода**  >  **Общие** " в окно свойств проекта. Параметры для настройки средства можно найти в подменю Clang-Tidy.

Дополнительные сведения см. [в разделе инструкции. Установка свойств анализа кода для проектов C/C++](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md).

## <a name="cmake"></a>CMake

В проектах CMak можно настроить проверки Clang-Tidy в `CMakeSettings.json` . После открытия выберите "изменить JSON" в правом верхнем углу редактора параметров проекта CMak. Распознаются следующие ключи:

- `enableMicrosoftCodeAnalysis`: Включает анализ кода Майкрософт
- `enableClangTidyCodeAnalysis`: Включает анализ Clang-Tidy
- `clangTidyChecks`: Clang-Tidy конфигурация, указанная в виде списка с разделителями-запятыми, то есть включает или отключает

Если не указано ни одного из параметров "включить", Visual Studio выберет средство анализа, соответствующее используемому набору инструментов платформы.

## <a name="warning-display"></a>Отображение предупреждений

Clang-Tidy запускаются в результате предупреждений, отображаемых в Список ошибок, а также как волнистые части в редакторе в соответствующих разделах кода. Используйте столбец Category (категория) в Список ошибок для сортировки и упорядочения предупреждений Clang-Tidy. Можно настроить предупреждения в редакторе, установив параметр "отключить неподчеркнутые коды анализа кода" в разделе **Сервис**  >  **Параметры** .

## <a name="clang-tidy-configuration"></a>Конфигурация Clang-Tidy

Можно настроить проверки, выполняемые Clang в Visual Studio с помощью параметра **Clang-configure checks** . Эти входные данные предоставляются **`--checks`** аргументу средства. Любую дальнейшую настройку можно добавить в пользовательские *`.clang-tidy`* файлы. Дополнительные сведения см. в [Clang документации по LLVM.org](https://clang.llvm.org/extra/clang-tidy/).

## <a name="see-also"></a>См. также статью

- [Поддержка Clang/LLVM для проектов MSBuild](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [Поддержка Clang/LLVM для проектов CMak](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end
