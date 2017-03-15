---
title: "_variant_t::Detach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::Detach"
  - "_variant_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach - метод"
  - "VARIANT - объект"
  - "VARIANT - объект, detatch"
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# _variant_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Отключает инкапсулированный объект **VARIANT** от данного объекта `_variant_t`.  
  
## Синтаксис  
  
```  
  
VARIANT Detach( );  
  
```  
  
## Возвращаемое значение  
 Инкапсулированный **VARIANT**.  
  
## Заметки  
 Извлекает и возвращает инкапсулированный **VARIANT**, а затем очищает данный объект `_variant_t` без его удаления.  Эта функция\-член удаляет **VARIANT** из инкапсуляции и задает для **VARTYPE** данного объекта `_variant_t` значение `VT_EMPTY`.  Решение о выпуске возвращаемого **VARIANT** путем вызова функции [VariantClear](http://msdn.microsoft.com/ru-ru/28741d81-8404-4f85-95d3-5c209ec13835) принимает разработчик.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_variant\_t](../cpp/variant-t-class.md)