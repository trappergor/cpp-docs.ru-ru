---
title: Справочник по MSBuild для проектов C++ в Visual Studio
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 854dc0554c327f191b4b4b9694548cdb9983c5f8
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826886"
---
# <a name="msbuild-reference-for-c-projects"></a>Справочник по MSBuild для проектов C++

MSBuild — система сборки в машинном для всех проектов в Visual Studio, включая проекты C++. При построении проекта в среде разработки Visual Studio (IDE), он вызывает средство msbuild.exe, которое в свою очередь использует VCXPROJ-файл проекта и различные файлы .targets и .props. Как правило настоятельно рекомендуется с помощью Visual Studio IDE для задания свойств проекта и вызвать MSBuild. Ручная настройка файлов проекта может привести к серьезным проблемам при неправильном.

Если для какой-то причине вы хотите использовать MSBuild непосредственно из командной строки, см. в разделе [использовать MSBuild из командной строки](../msbuild-visual-cpp.md). Как правило, Дополнительные сведения о MSBuild см. в разделе [MSBuild](/visualstudio/msbuild/msbuild) в документации по Visual Studio.

## <a name="in-this-section"></a>В данном разделе

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