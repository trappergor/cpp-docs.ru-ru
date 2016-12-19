---
title: "CreateProject | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CreateProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateProject - метод"
ms.assetid: b5598b46-fe29-4ad0-8bfe-a4dc789aeebd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreateProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает проект С\+\+.  
  
## Синтаксис  
  
```  
  
      function CreateProject(   
   strProjectName,   
   strProjectPath    
);  
```  
  
#### Параметры  
 `strProjectName`  
 Строка, содержащая имя проекта.  
  
 *strProjectPath*  
 Строка, содержащая путь проекта.  
  
## Возвращаемое значение  
 Объект проекта.  
  
## Заметки  
 Данная функция вызывается для создания проекта С\+\+, которые можно открыть в Visual Studio.  Если параметр контекста мастера **WizardType** задан как **vsWizardAddSubProject**, проект добавляется как вложенный проект к существующему проекту.  Дополнительные сведения содержатся в разделе [ContextParamsEnum](../Topic/Context%20Parameters%20for%20Launching%20Wizards.md).  
  
## Пример  
 См. раздел [AddFilesToProject](../Topic/AddFilesToProject.md).  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)