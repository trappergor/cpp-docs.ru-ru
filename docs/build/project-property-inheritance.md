---
title: Наследование свойств в проектах Visual Studio — C++
description: Наследование свойств в собственных (MSBuild) проектах Visual Studio на C++.
ms.date: 02/21/2020
helpviewer_keywords:
- C++ projects, property inheritance
ms.openlocfilehash: 17b23426f70bb2d306491e538d30cffc0f202362
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919219"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Наследование свойств в проектах Visual Studio

Собственная система проектов Visual Studio основана на MSBuild. Платформа MSBuild определяет форматы файлов и правила сборки проектов любого типа. Она в значительной степени упрощает сборку для нескольких платформ и конфигураций. Вам будет полезно разобраться в ее работе. Это особенно важно, если потребуется определять пользовательские конфигурации или создавать многоразовые наборы свойств, которые можно совместно использовать и импортировать в несколько проектов.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>Файл VCXPROJ, файлы PROPS и TARGETS

::: moniker range="msvc-140"

Свойства проекта хранятся в нескольких файлах. Некоторые из них находятся непосредственно в файле проекта *`.vcxproj`* . Другие свойства определяются в файлах *`.targets`* или *`.props`* , которые импортируются файлом проекта и содержат значения по умолчанию. Файлы проекта Visual Studio 2015 находятся в папке, соответствующей языковому стандарту, в базовом каталоге *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\v140`* .

::: moniker-end

::: moniker range="msvc-150"

Свойства проекта хранятся в нескольких файлах. Некоторые из них находятся непосредственно в файле проекта *`.vcxproj`* . Другие свойства определяются в файлах *`.targets`* или *`.props`* , которые импортируются файлом проекта и содержат значения по умолчанию. Файлы проекта Visual Studio 2017 находятся в папке, соответствующей языковому стандарту, в базовом каталоге *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`* .

::: moniker-end

::: moniker range=">=msvc-160"

Свойства проекта хранятся в нескольких файлах. Некоторые из них находятся непосредственно в файле проекта *`.vcxproj`* . Другие свойства определяются в файлах *`.targets`* или *`.props`* , которые импортируются файлом проекта и содержат значения по умолчанию. Файлы проекта Visual Studio находятся в папке, соответствующей языковому стандарту, в базовом каталоге *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>`* . Значение атрибута `<version>` зависит от версии Visual Studio. *`v160`* соответствует версии Visual Studio 2019.

::: moniker-end

Свойства также хранятся в любых пользовательских файлах *`.props`* , которые вы можете добавить в свой проект. Мы настоятельно рекомендуем *НЕ ИЗМЕНЯТЬ* эти файлы вручную. Если у вас нет четкого представления о работе MSBuild и строении файлов *`.vcxproj`* , используйте для изменения свойств, особенно участвующих в наследовании, страницы свойств в интегрированной среде разработки.

Как указано выше, одному свойству для некоторой конфигурации можно назначить разные значения в разных файлах. При сборке проекта модуль MSBuild оценивает файл проекта и все импортированные файлы в строго определенном порядке, который описывается ниже. По мере оценки каждого файла все значения свойств, определенные в этом файле, переопределяют существующие значения. Все неуказанные значения наследуются от файлов, оцененных ранее. При установке свойства с помощью страниц свойств важно также следить за тем, где именно вы это делаете. Если задать свойство X в файле *`.props`* , при том что для того же свойства задано значение Y в файле проекта, проект будет создан со свойством, имеющим значение Y. Если то же свойство имеет значение Z для элемента проекта, например файла *`.cpp`* , то модуль MSBuild использует значение Z.

Ниже представлено базовое дерево наследования.

1. Параметры по умолчанию из набора инструментов MSBuild CPP (файл *`Microsoft.Cpp.Default.props`* в базовом каталоге, который импортируется файлом *`.vcxproj`* )

1. Страницы свойств.

1. Файл *`.vcxproj`* . (Этот файл может переопределять параметры по умолчанию и параметры страницы свойств.)

1. Метаданные элементов.

> [!TIP]
> Свойство, выделенное **полужирным** шрифтом на странице свойств, определяется в текущем контексте. Свойство в обычном шрифте наследуется.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>Просмотр развернутого файла проекта со всеми импортированными значениями

Иногда полезно просмотреть развернутый файл, чтобы определить, как наследуется значение данного свойства. Для просмотра развернутой версии введите следующую команду в командной строке Visual Studio (замените заполнители на конкретные имена файлов).

> **msbuild /pp:** _temp_ **.txt** _myapp_ **.vcxproj**

Развернутые файлы проекта могут быть большими и трудными для понимания, если вы не знакомы с MSBuild. Ниже представлена основная структура файла проекта.

1. Основные свойства проекта, которые не представлены в интегрированной среде разработки.

1. Импорт файла *`Microsoft.cpp.default.props`* , который определяет некоторые базовые, независимые от набора инструментов свойства.

1. Глобальные свойства конфигурации (предоставляемые как свойства по умолчанию **PlatformToolset** и **Project** на странице **Конфигурация &gt; Общие** ). Эти свойства определяют, какие страницы свойств набора инструментов и встроенные страницы свойств будут импортироваться в *`Microsoft.cpp.props`* на следующем шаге.

1. Импорт файла *`Microsoft.cpp.props`* , который задает большинство значений проекта по умолчанию.

1. Импорт всех страниц свойств, включая файлы *`.user`* . Эти страницы свойств могут переопределить все значения, кроме свойств по умолчанию **PlatformToolset** и **Project**.

1. Остальная часть свойств конфигурации проекта. Эти значения могут переопределять значения, заданные на страницах свойств.

1. Элементы (файлы) вместе с связанными с ними метаданными. Эти элементы всегда используются последними в правилах вычисления MSBuild, даже если находятся до других свойств и импортов.

Дополнительные сведения см. в разделе [Свойства MSBuild](/visualstudio/msbuild/msbuild-properties).

## <a name="build-configurations"></a>Конфигурации сборки

Конфигурация — это просто произвольная группа свойств, которым назначено имя. Visual Studio предоставляет конфигурации отладки и выпуска. Каждая из них задает различные свойства соответственно для сборки отладки или выпуска. Вы можете использовать **Configuration Manager** для определения настраиваемых конфигураций. Так удобно группировать свойства для определенной конфигурации сборки.

Чтобы лучше разобраться в конфигурациях сборки, откройте **диспетчер свойств**. В зависимости от настроенных параметров его можно открыть, выбрав пункт **Вид > Диспетчер свойств** или **Вид > Другие окна > Диспетчер свойств**. В **диспетчере свойств** есть узлы для каждой пары конфигурации и платформы в проекте. В каждом из этих узлов находятся узлы для страниц свойств (файлы *`.props`* ), позволяющие задать некоторые свойства для этой конфигурации.

![Диспетчер свойств](media/property-manager.png "диспетчер свойств")

Например, можно перейти в область "Общие" на страницах свойств. Измените значение свойства "Кодировка" на "Не задано" вместо "Использовать Юникод" и нажмите кнопку **ОК**. В диспетчере свойств страницы свойств **Поддержка Юникода** больше не будет. Она удаляется для текущей конфигурации, но сохраняется для других.

Дополнительные сведения о диспетчере и страницах свойств см. в статье [Совместное или повторное использование параметров проекта Visual Studio C++](create-reusable-property-configurations.md).

> [!TIP]
> Файл *`.user`* является нерекомендуемым. Мы рекомендуем удалить его, чтобы обеспечить правильную группировку свойств по конфигурации и платформе.
