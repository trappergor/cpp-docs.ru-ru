---
title: "CanAddMFCClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddMFCClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddMFCClass - метод"
ms.assetid: 6a97a410-b028-4aad-9b06-04c12cf481eb
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddMFCClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывается мастером для проверки возможности добавления пользователем класса MFC в проект.  
  
## Синтаксис  
  
```  
  
      function CanAddMFCClass(   
   oProj,   
   oObject    
);  
```  
  
#### Параметры  
 `oProj`  
 Выбранный проект  
  
 `oObject`  
 Выбранный объект.  В данном случае это текущий проект.  
  
## Возвращаемое значение  
 Имеет значение **true**, если класс может быть добавлен; **false**, если пользователь вызывает функцию для проекта, не являющегося проектом MFC и не имеющего поддержки MFC.  
  
## Заметки  
 Вызывается мастером для проверки совместимости проекта с запускаемым мастером кодов \(иными словами, может ли проект принимать класс MFC\).  
  
 Мастер вызывает данную функцию, если в [файле элемента управления проекта .vsz](../ide/dot-vsz-file-project-control.md) имеется параметр PREPROCESS\_FUNCTION, и проверяет доступность объекта [модели кода Visual C\+\+](http://msdn.microsoft.com/ru-ru/dd6452c2-1054-44a1-b0eb-639a94a1216b).  Если модель кода недоступна, функция сообщает об ошибке и возвращает значение **false**.  
  
## Пример  
  
```  
// Determine if an MFC class can be added to the project  
if (CanAddMFCClass(selProj, selObj))  
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
 [Функция CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../Topic/IsMFCProject.md)