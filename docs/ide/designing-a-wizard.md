---
title: "Разработка мастера | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "пользовательские мастера [C++], разработка проектов"
  - "проекты [C++], пользовательские мастера"
  - "проекты Visual C++, пользовательские мастера"
  - "мастера [C++], пользовательский"
ms.assetid: a7c0be7e-9297-4fed-83e3-5645c896d56b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Разработка мастера
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возможно, вам потребуется создать проекты со стандартизированными функциями, которые отличаются от мастеров приложений, предоставленных в Visual C\+\+.  Для таких задач можно использовать архитектуру мастера Visual C\+\+, предназначенную для упрощения расширяемости и настройки.  Для создания мастера можно использовать [Специальный мастер Visual C\+\+](../ide/creating-a-custom-wizard.md).  После создания мастера можно настроить его на создание начальных файлов для проектов.  
  
 Мастер Visual C\+\+ является HTML\-элементом управления.  В нем используется обработчик мастера Visual C\+\+ <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>, предоставляющий общие службы, такие как <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.NavigateToCommandHandler%2A>, <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.OkCancelAlert%2A> и т. д.  В мастере используется также обработчик скриптов, позволяющий мастеру понимать как VBScript, так и [JScript .NET](http://msdn.microsoft.com/ru-ru/c7e636ee-c10f-45b1-85ec-fe2daca30bf5).  
  
 Архитектура мастера позволяет получить доступ к перечисленным ниже моделям объектов непосредственно в мастерах и вызывать их методы, свойства и события из файлов JScript или HTML\-файлов.  \(Дополнительные сведения см. в примерах, приведенных в разделах [HTML\-файлы](../ide/html-files.md) и [Файл JScript](../ide/jscript-file.md).\)  
  
-   [Модель объекта среды DTE](../Topic/Extending%20the%20Visual%20Studio%20Environment.md)  
  
-   [Модель кода Visual C\+\+](http://msdn.microsoft.com/ru-ru/dd6452c2-1054-44a1-b0eb-639a94a1216b)  
  
-   [Модель проекта Visual C\+\+](http://msdn.microsoft.com/ru-ru/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f)  
  
-   [Модель мастера Visual C\+\+](http://msdn.microsoft.com/ru-ru/159395ac-33c7-47bf-ad42-4e1435ddc758)  
  
 Описание каждого элемента процесса разработки мастера см. в разделе [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md).  
  
## См. также  
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Этапы проектирования мастера](../ide/steps-to-designing-a-wizard.md)   
 [Настройка мастера](../ide/customizing-your-wizard.md)