---
title: "Конструктор ComPtr::ComPtr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ComPtr
dev_langs: C++
helpviewer_keywords: ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b31fdcbad35bc65b2d8ca26ccab69e875c1d3aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comptrcomptr-constructor"></a>Конструктор ComPtr::ComPtr
Инициализирует новый экземпляр класса ComPtr. Перегрузки предоставляют конструкторы по умолчанию, конструкторы копирования, перемещения и преобразования.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `U`  
 Тип параметра `other`.  
  
 `other`  
 Объект типа `U`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор является конструктором по умолчанию, который неявно создает пустой объект. Второй конструктор определяет [__nullptr](../windows/nullptr-cpp-component-extensions.md), который явно создает пустой объект.  
  
 Третий конструктор создает объект из объекта, указанного при помощи указателя.  
  
 Четвертый и пятый конструкторы являются copy-конструкторами. Пятый конструктор копирует объект, если его преобразовать текущий тип.  
  
 Шестой и седьмой конструкторы являются конструкторы перемещения. Седьмой конструктор перемещает объект, если его преобразовать текущий тип.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)