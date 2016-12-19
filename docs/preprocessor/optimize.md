---
title: "optimize | Microsoft Docs"
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
  - "vc-pragma.optimize"
  - "optimize_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "optimize - прагма"
  - "прагмы, optimize"
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# optimize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает оптимизации, которые требуется выполнять для каждой функции.  
  
## Синтаксис  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## Заметки  
 Директива \#pragma **optimize** должна находиться за пределами функции и действует на первую функцию, определенную после этой директивы.  Аргументы **on** и **off** включают и выключают параметры, указанные в *списке\-оптимизации*.  
  
 *Список\-оптимизации* может содержать ноль или несколько параметров, приведенных в следующей таблице.  
  
### Параметры директивы \#pragma optimize  
  
|Параметры|Тип оптимизации|  
|---------------|---------------------|  
|**g**|Включить глобальную оптимизацию.|  
|**s** или **t**|Указывать короткую или быструю последовательность машинного кода.|  
|**y**|Создавать указатели фреймов в стеке программы.|  
  
 Эти же символы используются с параметрами компилятора [\/O](../build/reference/o-options-optimize-code.md).  Например, следующая директива \#pragma эквивалентна параметру компилятора **\/Os**:  
  
```  
#pragma optimize( "ts", on )  
```  
  
 Директива \#pragma **optimize** с пустой строкой \(**""**\) представляет собой специальную форму директивы.  
  
 При использовании параметра **off** она выключает оптимизации, перечисленные в таблице выше в этом разделе.  
  
 При использовании параметра **on** она снова устанавливает оптимизации, заданные с помощью параметра компилятора [\/O](../build/reference/o-options-optimize-code.md).  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)