---
title: "AddInterfaceFromFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AddInterfaceFromFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddInterfaceFromFile - метод"
ms.assetid: fa848690-ad98-4fb4-bbcf-dffcaad05df2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# AddInterfaceFromFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Воспроизводит и вставляет файл шаблона, содержащий интерфейс.  
  
## Синтаксис  
  
```  
  
      function AddInterfaceFromFile(   
   oCM,   
   strInterfaceFile    
);  
```  
  
#### Параметры  
 `oCM`  
 Объект [Visual C\+\+ Code Model](http://msdn.microsoft.com/ru-ru/dd6452c2-1054-44a1-b0eb-639a94a1216b).  
  
 *strInterfaceFile*  
 Только имя файла шаблона, без пути.  
  
## Заметки  
 Эта функция вызывается для воспроизведения и вставки в IDL\-файл проекта файл шаблона, содержащий интерфейс.  
  
 Если интерфейс не добавляется успешно, эта функция отображает сообщение об ошибке.  
  
## Пример  
  
```  
// Render myint.idl and insert into strProject.idl  
AddInterfaceFromFile(oCM, "myint.idl");  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)