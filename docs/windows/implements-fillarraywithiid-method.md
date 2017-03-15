---
title: "Метод Implements::FillArrayWithIid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid - метод"
ms.assetid: b2e62e3f-0ab9-4c70-aad7-856268544f44
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод Implements::FillArrayWithIid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вставляет идентификатор интерфейса, заданный текущим параметром шаблона zeroth в конкретный элемент массива.  
  
## Синтаксис  
  
```  
__forceinline static void FillArrayWithIid(  
   unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### Параметры  
 `index`  
 Индекс, начинающийся с нуля, указывающий начальный элемент массива для данной операции.  При завершении этой операции, `index` увеличивается на 1.  
  
 `iids`  
 Массив типа IID.  
  
## Примечания  
 Внутренняя вспомогательная функция.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Структура Implements](../Topic/Implements%20Structure.md)