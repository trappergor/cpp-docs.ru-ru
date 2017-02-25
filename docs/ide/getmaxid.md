---
title: "GetMaxID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetMaxID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMaxID - метод"
ms.assetid: a155ec2e-6132-4e40-9b85-d710538778a1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetMaxID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает наибольший идентификатор dispid из членов этого интерфейса и всех его базовых объектов.  
  
## Синтаксис  
  
```  
  
      function GetMaxID(   
   ointerface    
);  
```  
  
#### Параметры  
 *оinterface*  
 Объект <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeInterface>.  
  
## Возвращаемое значение  
 Наибольший идентификатор dispid из членов объекта *oInterface* и всех его базовых объектов.  
  
## Заметки  
 Эта функция вызывается для получения наибольшего идентификатора dispid из членов указанного интерфейса и всех его базовых объектов.  
  
## Пример  
  
```  
if (strInterfaceType == "custom")  
      window.external.AddSymbol("DISPID_DISABLED", true);  
   else  
   {  
      var nDispID = window.external.FindSymbol("DISPID");  
      if (!nDispID.length)  
      {  
         nDispID = GetMaxID(oInterface) + 1;  
         window.external.AddSymbol("DISPID", nDispID);  
      }  
   }  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)