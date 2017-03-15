---
title: "Оператор ComPtrRef::operator== | Microsoft Docs"
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
  - "client/Microsoft::WRL::Details::ComPtrRef::operator=="
dev_langs: 
  - "C++"
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор ComPtrRef::operator==
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```cpp  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator==(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### Параметры  
 `a`  
 Ссылка на объект ComPtrRef.  
  
 `b`  
 Ссылка на другой объект ComPtrRef или указатель на анонимный тип \(`void*`\).  
  
## Возвращаемое значение  
 Первый оператор возвращает `true`, если объект `a` равен объекту `b`; в противном случае `false`.  
  
 Второй и третий операторы возвращают `true`, если объект `a` равен `nullptr`; в противном случае `false`.  
  
 Четвертый и пятые операторы возвращают `true`, если объект `a` равен объекту `b`; в противном случае `false`.  
  
## Заметки  
 Указывает, равны ли два объекта ComPtrRef.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)   
 [Класс ComPtrRef](../Topic/ComPtrRef%20Class.md)