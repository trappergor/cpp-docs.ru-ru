---
title: Справочник по MSBuild C++ для проектов в Visual Studio
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: ec1285a760d438a94863181a1b099e6db153c268
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168906"
---
# <a name="msbuild-reference-for-c-projects"></a>Проекты С++. Справочник по MSBuild

MSBuild — это собственная система сборки для всех проектов в Visual Studio, включая C++ проекты. При построении проекта в интегрированной среде разработки (IDE) Visual Studio вызывается средство MSBuild. exe, которое, в свою очередь, использует файл проекта с расширением VCXPROJ, а также различные файлы targets и PROPS. Как правило, мы настоятельно рекомендуем использовать интегрированную среду разработки Visual Studio для установки свойств проекта и вызова MSBuild. Изменение файлов проекта вручную может привести к серьезным проблемам, если они не были выполнены правильно.

Если по некоторым причинам вы хотите использовать MSBuild непосредственно из командной строки, см. раздел [Использование MSBuild из командной строки](../msbuild-visual-cpp.md). Дополнительные сведения о MSBuild см. в разделе [MSBuild](/visualstudio/msbuild/msbuild) в документации по Visual Studio.

## <a name="in-this-section"></a>В этом разделе

[Проекты С++. Внутренние компоненты MSBuild](msbuild-visual-cpp-overview.md)<br/>
Сведения о хранении и использовании свойств и целевых объектов.

[Стандартные макросы для команд и свойств сборки](common-macros-for-build-commands-and-properties.md)<br/>
Описывает макросы (константы времени компиляции), которые можно использовать для определения таких свойств, как пути и версии продукта.

[Типы файлов, созданные C++ для проектов](file-types-created-for-visual-cpp-projects.md)<br/>
Описывает различные типы файлов, создаваемые Visual Studio для различных типов проектов.

[Шаблоны проектов C++ Visual Studio](visual-cpp-project-types.md)<br>
Описывает типы проектов на основе MSBuild, доступные для C++.

[Новые шаблоны элементов C++](using-visual-cpp-add-new-item-templates.md)<br>
Описывает исходные файлы и другие элементы, которые можно добавить в проект Visual Studio.

[Файлы предкомпилированных заголовков](../creating-precompiled-header-files.md) Использование предварительно скомпилированных файлов заголовков и создание собственного пользовательского предкомпилированного кода для ускорения времени сборки.

[Справочник по свойствам проекта Visual Studio](property-pages-visual-cpp.md)<br/>
Справочная документация по свойствам проекта, заданным в интегрированной среде разработки Visual Studio.

## <a name="see-also"></a>См. также раздел

[Справочные сведения о сборке C/C++](c-cpp-building-reference.md)
