---
title: "Функция CanAddATLClass | Microsoft Docs"
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
  - "CanAddATLClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddATLClass - метод"
ms.assetid: 7a8abf90-c1b8-475c-af22-7948478084f9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция CanAddATLClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывается мастером для проверки, может ли пользователь добавить класс ATL в проект.  
  
## Синтаксис  
  
```  
  
      function CanAddATLClass(   
   oProj,   
   oObject    
);  
```  
  
#### Параметры  
 `oProj`  
 Выбранный проект.  
  
 `oObject`  
 Выбранный объект.  В данном случае это текущий проект.  
  
## Возвращаемое значение  
 Значение **true**, если класс можно добавить; значение **false**, если пользователь вызывает функцию для проекта, не являющегося проектом ATL и не поддерживающего ATL.  
  
## Заметки  
 Вызывается мастером для проверки совместимости проекта с запускаемым мастером кодов \(иными словами, может ли проект принимать класс ATL\).  
  
 Мастер вызывает данную функцию, если в [VSZ\-файле элемента управления проекта](../ide/dot-vsz-file-project-control.md) имеется параметр PREPROCESS\_FUNCTION, и проверяет доступность объекта [модели кода Visual C\+\+](http://msdn.microsoft.com/ru-ru/dd6452c2-1054-44a1-b0eb-639a94a1216b).  Если модель кода недоступна, функция сообщает об ошибке и возвращает значение **false**.  
  
## Пример  
  
```  
// Determine if an ATL class can be added to the project  
if (CanAddATLClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [Функция CanAddClass](../ide/canaddclass.md)   
 [IsMFCProject](../Topic/IsMFCProject.md)   
 [CanAddMFCClass](../ide/canaddmfcclass.md)