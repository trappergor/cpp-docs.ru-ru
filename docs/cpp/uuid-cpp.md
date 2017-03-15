---
title: "uuid (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "uuid"
  - "uuid_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++], uuid"
  - "uuid __declspec - ключевое слово"
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Компилятор добавляет идентификатор GUID в класс или структуру, объявленные или определенные \(только полные определения COM\-объекта\) с атрибутом `uuid`.  
  
## Синтаксис  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## Заметки  
 Атрибут `uuid` принимает строку в качестве аргумента.  Эта строка именует идентификатор GUID в обычном формате реестра с разделителями **{ }** или без них.  Например:  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 Этот атрибут можно применить при повторном объявлении.  Это позволяет заголовкам системы предоставлять определения интерфейсов, например **IUnknown**, и гарантировать повторное объявление в другом заголовке \(например, COMDEF.H\) для предоставления идентификатора GUID.  
  
 Ключевое слово [\_\_uuidof](../cpp/uuidof-operator.md) можно применить для извлечения постоянного идентификатора GUID, добавленного в пользовательский тип.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)