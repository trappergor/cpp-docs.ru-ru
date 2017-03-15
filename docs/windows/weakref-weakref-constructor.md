---
title: "Конструктор WeakRef::WeakRef | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::WeakRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakRef, конструктор"
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Конструктор WeakRef::WeakRef
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует новый экземпляр класса WeakRef.  
  
## Синтаксис  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
#### Параметры  
 `ptr`  
 Указатель, ссылка или rvalue\-ссылка на существующий объект, который инициализирует текущий объект WeakRef.  
  
## Примечания  
 Первый конструктор инициализирует пустой объект WeakRef.  Второй конструктор инициализирует объект WeakRef из указателя на интерфейс IWeakReference.  Третий конструктор инициализирует объект WeakRef из ссылки на объект ComPtr\< IWeakReference\>.  Четвертый и пятый конструктор инициализируют объект WeakRef из другого объекта WeakRef.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс WeakRef](../windows/weakref-class.md)