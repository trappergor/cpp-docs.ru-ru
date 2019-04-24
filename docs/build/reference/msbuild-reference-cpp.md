---
title: Справочник по MSBuild для проектов C++ в Visual Studio
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: b6ec6b5d276cb7104cf61c229476596d2a2a7684
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024703"
---
# <a name="msbuild-reference-for-c-projects"></a>Справочник по MSBuild для проектов C++

MSBuild — система сборки в машинном для всех проектов в Visual Studio, включая проекты C++. При построении проекта в среде разработки Visual Studio (IDE), он вызывает средство msbuild.exe, которое в свою очередь использует VCXPROJ-файл проекта и различные файлы .targets и .props. Как правило настоятельно рекомендуется с помощью Visual Studio IDE для задания свойств проекта и вызвать MSBuild. Ручная настройка файлов проекта может привести к серьезным проблемам при неправильном.

Если для какой-то причине вы хотите использовать MSBuild непосредственно из командной строки, см. в разделе [использовать MSBuild из командной строки](../msbuild-visual-cpp.md). Как правило, Дополнительные сведения о MSBuild см. в разделе [MSBuild](/visualstudio/msbuild/msbuild) в документации по Visual Studio.

## <a name="in-this-section"></a>Содержание раздела

[Проекты С++. Внутренние компоненты MSBuild](msbuild-visual-cpp-overview.md)<br/>
Сведения о том, как свойства и целевые объекты будут храниться и использоваться.

[Стандартные макросы для команд и свойств сборки](common-macros-for-build-commands-and-properties.md)<br/>
Описывает макросы (константы времени компиляции), которые могут использоваться для определения свойства, такие как пути и версий продукта.

[Типы файлов, создаваемых для проектов C++](file-types-created-for-visual-cpp-projects.md)<br/>
Описание различных типов файлов, которые Visual Studio создает для различных типов проектов.

[Шаблоны проектов Visual Studio C++](visual-cpp-project-types.md)<br>
Описывает типы основан на MSBuild, которые доступны для C++.

[Новые шаблоны элементов C++](using-visual-cpp-add-new-item-templates.md)<br>
Описывает исходные файлы и другие элементы, которые можно добавить в проект Visual Studio.

[Файлы предкомпилированных заголовков](../creating-precompiled-header-files.md) о том, как использовать файлы предварительно скомпилированных заголовков и как создать собственный пользовательский предварительно скомпилированного кода, чтобы ускорить время сборки.

[Ссылка свойства проекта Visual Studio](property-pages-visual-cpp.md)<br/>
Справочная документация для свойств проекта, которые были заданы в интегрированной среде разработки Visual Studio.

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](c-cpp-building-reference.md)