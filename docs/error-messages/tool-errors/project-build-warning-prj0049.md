---
title: Проект сборки предупреждение при PRJ0049 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 169ba63318f630ac6a63b18d34fd6a7d829f4f90
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110891"
---
# <a name="project-build-warning-prj0049"></a>Предупреждение при построении проекта PRJ0049

Упоминаемого целевого "\<ссылка >" требуется платформа .NET Framework \<MinFrameworkVersion > и не сможет запуститься на целевой платформы этого проекта

Приложения, созданные с помощью Visual Studio 2008 можно указать, какая версия .NET Framework, которые они должны ориентироваться. Если добавить ссылку на сборку или проект, который зависит от версии платформы .NET Framework, которая старше целевой версии, вы получите это предупреждение во время компиляции.

### <a name="to-correct-this-warning"></a>Чтобы устранить это предупреждение

1. Выберите один из следующих вариантов.

   - Изменение целевой версии .NET framework в проекте **страницы свойств** диалоговое окно, так как это превышающую минимально допустимая версия для всех указанных сборок и проектов. Дополнительные сведения см. в разделе [Добавление ссылок](../../ide/adding-references-in-visual-cpp-projects.md).

   - Удалите ссылку на сборку или проект, минимально допустимая версия, которая старше целевой версии .NET framework. Эти объекты помечаются значком предупреждения в проекте **страницы свойств**.

## <a name="see-also"></a>См. также

[Ошибки и предупреждения режима сборки проекта (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)