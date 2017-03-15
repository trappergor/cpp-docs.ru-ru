---
title: "Класс marshal_context | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context - класс [C++]"
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс marshal_context
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот класс преобразует данные размещения между управляемыми и сред.  
  
## Синтаксис  
  
```  
class marshal_context  
```  
  
## Заметки  
 Используйте класс `marshal_context` для преобразований данных, требующих контекста.  Дополнительные сведения см. в разделе [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md) о которых преобразования требуется контекста и файл маршалинга, должен быть включен.  Результат маршалинга при использовании контекст допустим только до тех пор, пока объект `marshal_context` не уничтожается.  Чтобы сохранить, результат, необходимо скопировать данные.  
  
 То же `marshal_context` можно использовать для нескольких преобразований данных.  Повторно использовать контекст таким образом не влияет на результаты из предыдущих вызовов маршалинга.  
  
## Требования  
 **Файл заголовка.** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>или \<msclr\\marshal\_cppstd.h\>\<msclr\\marshal\_atl.h\>  
  
 **Пространство имен:** msclr::interop  
  
## См. также  
 [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)