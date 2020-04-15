---
title: Ссылка на MSBuild для проектов СЗЗ в Visual Studio
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: 96987a252d12f718025dd55deecad5c6bac26872
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336212"
---
# <a name="msbuild-reference-for-c-projects"></a>Проекты С++. Справочник по MSBuild

MSBuild является родной системой сборки для всех проектов в Visual Studio, в том числе проектов СЗ. При построении проекта в интегрированной среде разработки Visual Studio (IDE) он вызывает инструмент msbuild.exe, который, в свою очередь, потребляет файл проекта .vcxproj, а также различные файлы проекта .targets и .props. В целом, мы настоятельно рекомендуем использовать Visual Studio IDE для установки свойств проекта и вызывать MSBuild. Ручное редактирование файлов проекта может привести к серьезным проблемам, если не сделано правильно.

Если по какой-то причине вы хотите использовать MSBuild непосредственно с командной строки, [см.](../msbuild-visual-cpp.md) Для получения дополнительной информации о MSBuild в целом, см [MSBuild](/visualstudio/msbuild/msbuild) в visual Studio документации.

## <a name="in-this-section"></a>В этом разделе

[Внутренние компоненты MSBuild для проектов C++](msbuild-visual-cpp-overview.md)<br/>
Информация о том, как сохраняются и потребляются свойства и цели.

[Общие макросы для команд и свойств сборки](common-macros-for-build-commands-and-properties.md)<br/>
Описывает макросы (константы компиляции времени), которые могут быть использованы для определения свойств, таких как пути и версии продукта.

[Типы файлов, созданные для проектов СЗЗ](file-types-created-for-visual-cpp-projects.md)<br/>
Описывает различные типы файлов, которые Visual Studio создает для различных типов проектов.

[Шаблоны проектов Visual Studio](visual-cpp-project-types.md)<br>
Описывает типы проектов на основе MSBuild, доступные для СЗ.

[Новые шаблоны элементов C++](using-visual-cpp-add-new-item-templates.md)<br>
Описывает исходные файлы и другие элементы, которые можно добавить в проект Visual Studio.

[Предварительно собранные файлы заголовка](../creating-precompiled-header-files.md) Как использовать предварительно собранные файлы заголовка и как создать свой собственный предсборникный код для ускорения времени сборки.

[Ссылка на свойство проекта Visual Studio](property-pages-visual-cpp.md)<br/>
Справочная документация для свойств проекта, установленных в IDE Visual Studio.

## <a name="see-also"></a>См. также раздел

[Ссылка на сборку C/C++](c-cpp-building-reference.md)
