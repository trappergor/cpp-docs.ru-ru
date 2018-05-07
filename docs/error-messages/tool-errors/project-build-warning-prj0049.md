---
title: Проекта PRJ0049 предупреждение сборки | Документы Microsoft
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
ms.openlocfilehash: 8df6fcb8bc5d6517a46279e0bef5036db1e81241
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-warning-prj0049"></a>Предупреждение при построении проекта PRJ0049
Упоминаемого целевого "\<ссылка >" требуется платформа .NET Framework \<MinFrameworkVersion > и не сможет запуститься на целевой платформы этого проекта  
  
 Приложения, созданные с помощью Visual Studio 2008 можно указать версию [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] они предназначены. Если добавить ссылку на сборку или проект, который зависит от версии [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] , более поздней, чем целевая версия, вы получите это предупреждение во время компиляции.  
  
### <a name="to-correct-this-warning"></a>Чтобы устранить это предупреждение  
  
1.  Выберите один из следующих вариантов.  
  
    -   Изменение целевой версии .NET framework в проекте **страницы свойств** диалоговое окно, чтобы он является более поздней, чем или равно Минимально допустимая версия все связанные сборки и проекты. Дополнительные сведения см. в разделе [Добавление ссылок на](../../ide/adding-references-in-visual-cpp-projects.md).  
  
    -   Удалите ссылку на сборку или проект, минимально допустимая версия новее, чем целевой версии .NET framework. Эти объекты помечаются значком предупреждения в проекте **страницы свойств**.  
  
## <a name="see-also"></a>См. также  
 [Ошибки и предупреждения режима сборки проекта (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)