---
title: Использование Clang-Tidy в визуальной студии
description: Как использовать Clang-Tidy в Visual Studio для анализа кода Microsoft C.
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
author: frozenpandaman
ms.author: efessler
ms.openlocfilehash: ff32f522eaacee67e19aedaa1153b2c68edc98d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355153"
---
# <a name="using-clang-tidy-in-visual-studio"></a>Использование Clang-Tidy в визуальной студии

::: moniker range="<=vs-2017"

Поддержка Clang-Tidy требует Visual Studio 2019 версии 16.4 или позже. Чтобы увидеть документацию для этой версии, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end

::: moniker range=">=vs-2019"

Code Analysis намеренно поддерживает [Clang-Tidy](https://clang.llvm.org/extra/clang-tidy/) как для проектов MSBuild, так и для CMake, будь то с использованием инструментов Clang или MSVC. Проверки Clang-Tidy могут проводиться в рамках анализа фонового кода. Они отображаются в виде предупреждений в редакторе (squiggles) и отображаются в списке ошибок.

Поддержка Clang-Tidy доступна начиная с версии Visual Studio 2019 16.4. Он автоматически включается при выборе рабочей нагрузки в visual Studio Installer.

Clang-Tidy является инструментом анализа по умолчанию при использовании набора инструментов LLVM/clang-cl, доступного как в MSBuild, так и в CMake. Вы можете настроить его при использовании набора инструментов MSVC для запуска вместе со стандартным опытом анализа кода. Если вы используете набор инструментов clang-cl, анализ кода Майкрософт недоступен.

Clang-Tidy работает после успешной компиляции. Возможно, вам придется устранить ошибки исходного кода, чтобы получить результаты Clang-Tidy.

## <a name="msbuild"></a>MSBuild

Можно настроить Clang-Tidy для запуска как часть анализа кода, так и построить под**общей** страницей **анализа** > кода в окне свойств проекта. Варианты настройки инструмента можно найти под подменю Clang-Tidy.

Для получения дополнительной информации [см.](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md)

## <a name="cmake"></a>CMake

В проектах CMake вы можете настроить чеки `CMakeSettings.json`Clang-Tidy в пределах . После открытия щелкните кнопку "Edit JSON" в правом верхнем углу редактора настроек проекта CMake. Следующие ключи признаются:

- `enableMicrosoftCodeAnalysis`: Позволяет анализкодать кода Майкрософт
- `enableClangTidyCodeAnalysis`: Позволяет анализ Clang-Tidy
- `clangTidyChecks`: Конфигурация Clang-Tidy, указанная как список, разделенный запятой, то есть, проверки, которые будут включены или отключены

Если ни один из вариантов "включить" не указан, Visual Studio выберет инструмент анализа, соответствующий используемому набору инструментов Платформы.

## <a name="warning-display"></a>Предупреждающий дисплей

Запуски Clang-Tidy приводят к предупреждениям, отображаемым в списке ошибок, и в виде того, что в редакторе завихряются под соответствующими разделами кода. Используйте столбец "Категория" в списке ошибок для сортировки и организации предупреждений Clang-Tidy. Вы можете настроить в редакторе предупреждения, переключив настройки "Анализ изстроя кода" под параметры **Tools** > **Options.**

## <a name="clang-tidy-configuration"></a>Конфигурация Clang-Tidy

Вы можете настроить проверки, которые clang-tidy работает внутри Visual Studio через **clang-Tidy Проверки** вариант. Этот вход предоставляется **аргументу --проверяет** инструмент. Любая дальнейшая конфигурация *`.clang-tidy`* может быть включена в пользовательские файлы. Для получения дополнительной [информации, см Clang-Tidy документации на LLVM.org](https://clang.llvm.org/extra/clang-tidy/).

## <a name="see-also"></a>См. также раздел

- [Поддержка Clang/LLVM для проектов MSBuild](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [Поддержка Clang/LLVM для проектов CMake](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end
