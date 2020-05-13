---
title: 'Как: Изменить свойства и цели проекта СЗ без изменения файла проекта'
ms.date: 11/28/2018
helpviewer_keywords:
- project properties [C++], modifying outside project file
ms.openlocfilehash: 72107b572e35f222c0b03959e0edd2d23bd0130a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328460"
---
# <a name="how-to-modify-c-project-properties-and-targets-without-changing-the-project-file"></a>Как: Изменить свойства и цели проекта СЗ без изменения файла проекта

Вы можете переопределить свойства проекта и целевые объекты из командной строки MSBuild, не изменяя файл проекта. Это удобно в том случае, если вы хотите применять некоторые свойства лишь временно или периодически. Для этого нужно обладать некоторыми знаниями о MSBuild. Дополнительные сведения см. в разделе [MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild).

> [!IMPORTANT]
> Для создания файла PROPS или TARGETS можно использовать редактор XML в Visual Studio или любой текстовый редактор. Не используйте **диспетчер свойств** в этом сценарии, так как он добавляет свойства в файл проекта.

*Переопределение свойств проекта*

1. Создайте файл PROPS, задающий свойства, которые нужно переопределить.

1. В командной строке укажите: set ForceImportBeforeCppTargets="C:\sources\my_props.props".

*Переопределение целевых объектов проекта*

1. Создайте файл TARGETS с соответствующей реализацией или конкретным целевым объектом.

2. В командной строке укажите: set ForceImportAfterCppTargets ="C:\sources\my_target.targets".

Вы также можете задать любой параметр в командной строке MSBuild с помощью параметра "/p:".

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props"
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets"
```

В этом случае переопределение свойств и целевых объектов эквивалентно добавлению следующих операций импорта во все файлы VCXPROJ в решении.

```cmd
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```
