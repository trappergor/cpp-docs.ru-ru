---
title: "_variant_t::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::Attach"
  - "_variant_t.Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach - метод"
  - "VARIANT - объект"
  - "VARIANT - объект, присоединение"
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Помещает объект **VARIANT** в объект `_variant_t`.  
  
## Синтаксис  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### Параметры  
 *varSrc*  
 Объект **VARIANT**, который помещается в объект `_variant_t`.  
  
## Заметки  
 Инкапсулировав объект **VARIANT**, получает право на владение им.  Эта функция\-член освобождает все существующие инкапсулированные объекты **VARIANT**, затем копирует переданный объект **VARIANT** и устанавливает для его **VARTYPE** значение `VT_EMPTY`, чтобы его ресурсы мог освободить только деструктор `_variant_t`.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_variant\_t](../cpp/variant-t-class.md)