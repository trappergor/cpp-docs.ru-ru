---
title: "Оператор DontUseNewUseMake::operator new | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator new - оператор"
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Оператор DontUseNewUseMake::operator new
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### Параметры  
 `__unnamed0`  
 Неименованный параметр, который определяет количество байт памяти для выделения.  
  
 `placement`  
 Выделяемый тип.  
  
## Возвращаемое значение  
 Предоставляет способ передачи дополнительных аргументов при перегрузке оператора `new`.  
  
## Заметки  
 Перегружает оператор `new` и препятствует его использованию в RuntimeClass.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Класс DontUseNewUseMake](../windows/dontusenewusemake-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)