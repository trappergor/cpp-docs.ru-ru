---
title: Конструктор ComPtr::ComPtr | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr, constructor
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3a632c96c39ccd40f008556287af95944530cdc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871179"
---
# <a name="comptrcomptr-constructor"></a>Конструктор ComPtr::ComPtr
Инициализирует новый экземпляр класса ComPtr. Перегрузки предоставляют конструкторы по умолчанию, конструкторы копирования, перемещения и преобразования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<class U>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<class U>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<class U>  
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