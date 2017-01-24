---
title: "Оператор ComPtr::operator!= | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator!="
dev_langs: 
  - "C++"
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор ComPtr::operator!=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет неравенство двух объектов СomPtr.  
  
## Синтаксис  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### Параметры  
 `a`  
 Ссылка на объект ComPtr.  
  
 `b`  
 Ссылка на другой объект ComPtr.  
  
## Возвращаемое значение  
 Первый оператор возвращает `true`, если объект `a` не равен объекту `b`; в противном случае `false`.  
  
 Второй и третий операторы возвращают `true`, если объект `a` не равен `nullptr`; в противном случае `false`.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)   
 [Класс ComPtr](../windows/comptr-class.md)