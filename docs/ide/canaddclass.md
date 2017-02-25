---
title: "Функция CanAddClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddClass - метод"
ms.assetid: 76739742-1e34-470c-910d-8784f0adfbf0
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Функция CanAddClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывается мастером для проверки совместимости проекта с мастером кода, который пытается выполнить пользователь.  
  
## Синтаксис  
  
```  
  
      function CanAddClass(   
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
 Значение **true** если класс может быть добавлен; в противном случае значение **false**.  
  
## Заметки  
 Мастер вызывает данную функцию, если в [VSZ\-файле элемента управления проекта](../ide/dot-vsz-file-project-control.md) имеется параметр PREPROCESS\_FUNCTION.  
  
 Мастер также проверяет, доступен ли объект [модель кода Visual C\+\+](http://msdn.microsoft.com/ru-ru/dd6452c2-1054-44a1-b0eb-639a94a1216b).  Если модель кода недоступна, функция сообщает об ошибке и возвращает значение **false**.  
  
## Пример  
  
```  
// Determine if a class can be added to the project  
if (CanAddClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [CanAddMFCClass](../ide/canaddmfcclass.md)   
 [Функция CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../Topic/IsMFCProject.md)