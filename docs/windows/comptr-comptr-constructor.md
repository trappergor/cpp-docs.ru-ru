---
title: Конструктор ComPtr::ComPtr | Документация Майкрософт
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
ms.openlocfilehash: 86b55d8288f44b04ac1afc30a0afd67fce4edf81
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646777"
---
# <a name="comptrcomptr-constructor"></a>Конструктор ComPtr::ComPtr
Инициализирует новый экземпляр класса **ComPtr** класса. Перегрузки предоставляют конструкторы по умолчанию, конструкторы копирования, перемещения и преобразования.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
### <a name="parameters"></a>Параметры  
 *U*  
 Тип *других* параметра.  
  
 *other*  
 Объект типа *U*.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор является конструктором по умолчанию, который неявно создает пустой объект. Второй конструктор определяет [__nullptr](../windows/nullptr-cpp-component-extensions.md), который явно создает пустой объект.  
  
 Третий конструктор создает объект из объекта, указанного с помощью указателя.  
  
 Четвертый и пятый конструкторы являются конструкторами копий. Пятый конструктор копирует объект, если оно преобразуется в текущий тип.  
  
 Шестой и седьмой конструкторы являются конструкторы перемещения. Седьмой конструктор перемещает объект, если оно преобразуется в текущий тип.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)