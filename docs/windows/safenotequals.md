---
title: SafeNotEquals | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeNotEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeNotEquals function
ms.assetid: 032e45a8-4159-4b55-b7cc-ecd27f4e4788
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37f9627e301831c98ccab7a0c79258d96c520f1a
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605140"
---
# <a name="safenotequals"></a>SafeNotEquals
Определяет, если числа не равны.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeNotEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *t*  
 Первое число для сравнения. Это должен быть типа `T`.  
  
 [in] *u*  
 Второе число для сравнения. Это должен быть типа `U`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если *t* и *u* не равны; в противном случае **false**.  
  
## <a name="remarks"></a>Примечания  
 Метод улучшает `!=` поскольку **SafeNotEquals** позволяет сравнить две различных типов чисел.  
  
 Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для операции одно сравнение, без создания экземпляра [класс SafeInt](../windows/safeint-class.md).  
  
> [!NOTE]
>  Этот метод должен использоваться только в тех случаях, когда одной математической операции должны быть защищены. При наличии нескольких операций, следует использовать `SafeInt` класса вместо вызова отдельных автономных функций.  
  
 Дополнительные сведения о типах шаблонов `T` и `U`, см. в разделе [функции SafeInt](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** Microsoft::Utilities  
  
## <a name="see-also"></a>См. также  
 [Функции SafeInt](../windows/safeint-functions.md)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)   
 [SafeEquals](../windows/safeequals.md)