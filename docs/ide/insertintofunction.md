---
title: "InsertIntoFunction | Microsoft Docs"
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
  - "InsertIntoFunction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InsertIntoFunction - метод"
ms.assetid: 50500c3c-bee3-4a9c-a403-7dcd752de23c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InsertIntoFunction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используется функцией [AddATLSupportToProject](../ide/addatlsupporttoproject.md) для вставки кода в [InitInstance](../Topic/CWinApp::InitInstance.md).  
  
## Синтаксис  
  
```  
  
      function InsertIntoFunction(   
   oFunction,   
   strSearchString,   
   nStartLine,   
   nEndLine,   
   bInsideIfBlock    
);  
```  
  
#### Параметры  
 *oFunction*  
 Объект\-функция, в которую производится вставка.  
  
 `strSearchString`  
 Искомая строка для определения точки вставки.  
  
 *nStartLine*  
 Начальная строка кода, передаваемого функции [GetCodeForInitInstance](../ide/getcodeforinitinstance.md).  
  
 *nEndLine*  
 Конечная строка кода, передаваемого функции [GetCodeForInitInstance](../ide/getcodeforinitinstance.md).  
  
 *bInsideIfBlock*  
 Указывает на то, производится ли вставка в блок функции.  
  
## Возвращаемое значение  
 Возвращает значение **true** в случае успешного выполнения; в противном случае возвращает значение **false**.  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [GetMemberfunction](../Topic/GetMemberfunction.md)