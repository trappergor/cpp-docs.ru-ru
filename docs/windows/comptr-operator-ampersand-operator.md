---
title: "Оператор ComPtr::operator&amp; | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator& - оператор"
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор ComPtr::operator&amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Освобождает интерфейс, связанный с этим объектом `ComPtr`, а затем извлекает адрес объекта `ComPtr`.  
  
## Синтаксис  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## Возвращаемое значение  
 Слабая ссылка на текущий `ComPtr`.  
  
## Заметки  
 Этот метод отличается от [ComPtr::GetAddressOf](../Topic/ComPtr::GetAddressOf%20Method.md) тем, что данный метод освобождает ссылку на указатель интерфейса.  Используйте `ComPtr::GetAddressOf`, если требуется адрес указателя интерфейса, но не требуется освобождать интерфейс.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)