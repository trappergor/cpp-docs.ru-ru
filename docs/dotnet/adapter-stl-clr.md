---
title: "adapter (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/adapter>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<adapter> заголовок [STL/CLR]"
  - "<cliext/adapter> - заголовок [STL/CLR]"
  - "адаптер [STL/CLR]"
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Заголовок `<cliext/adapter>` STL\/CLR определяет 2 класса шаблона \(`collection_adapter` и `range_adapter`\) и функции шаблона `make_collection`.  
  
## Синтаксис  
  
```  
#include <cliext/adapter>  
```  
  
## Заметки  
  
|Класс|Описание|  
|-----------|--------------|  
|[collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md)|Создается коллекция \(BCL\) библиотеки базового класса в виде диапазона.|  
|[range\_adapter](../dotnet/range-adapter-stl-clr.md)|Создает диапазон как коллекция BCL.|  
  
|Функция|Описание|  
|-------------|--------------|  
|[make\_collection](../dotnet/make-collection-stl-clr.md)|Создает адаптер диапазона с помощью пары итератора.|  
  
## Требования  
 **Заголовок:**\<cliext\/adapter\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)