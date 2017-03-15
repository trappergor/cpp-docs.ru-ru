---
title: "Конструктор ComPtr::ComPtr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::ComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtr, конструктор"
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Конструктор ComPtr::ComPtr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует новый экземпляр класса ComPtr.  Перегрузки предоставляют конструкторы по умолчанию, копирования, перемещения и преобразования.  
  
## Синтаксис  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### Параметры  
 `U`  
 Тип параметра `other`.  
  
 `other`  
 Объект типа `U`.  
  
## Возвращаемое значение  
  
## Заметки  
 Первый конструктор является конструктором по умолчанию, который неявно создает пустой объект.  Второй конструктор определяет [\_\_nullptr](../windows/nullptr-cpp-component-extensions.md), который явным образом создает пустой объект.  
  
 Третий конструктор создает объект из определенного указателем объекта.  
  
 Четвертый и пятый конструкторы являются конструкторами копирования.  Пятый конструктор копирует объект, если он может быть преобразован к текущему типу.  
  
 Шестой и седьмой конструкторы являются конструкторами перемещения.  Седьмой конструктор перемещает объект, если он может быть преобразован к текущему типу.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)