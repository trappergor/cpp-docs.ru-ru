---
title: "Предупреждение при построении проекта PRJ0049 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0049"
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Предупреждение при построении проекта PRJ0049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указанный целевой '\<Reference\>' объект для платформы .NET Framework \<MinFrameworkVersion\> и невозможности запуска на требуемую версию .NET Framework этого проекта  
  
 Для приложений [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] можно задать версию [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)], для которой они предназначены.  Это предупреждение отображается во время компиляции при попытке добавления ссылки на сборку или проект, в которых используется более поздняя, чем в текущем проекте, версия [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)].  
  
### Устранение этого предупреждения  
  
1.  Выберите один из следующих вариантов.  
  
    -   В диалоговом окне **Страницы свойств** проекта задайте текущую версию .NET Framework, превышающую минимально допустимую для всех сборок и проектов, на которые существуют ссылки.  Для получения дополнительной информации см. [Добавление ссылок](../../ide/adding-references-in-visual-cpp-projects.md).  
  
    -   Удалите ссылку на сборку или проект, в которых используется более поздняя минимально допустимая версия .NET Framework, чем в текущем проекте.  В диалоговом окне **Страницы свойств** эти объекты помечаются значком предупреждения.  
  
## См. также  
 [Ошибки и предупреждения режима построения проекта \(PRJxxxx\)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)