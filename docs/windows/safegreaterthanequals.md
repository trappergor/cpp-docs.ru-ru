---
title: SafeGreaterThanEquals | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeGreaterThanEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeGreaterThanEquals function
ms.assetid: 43312fa9-d925-4f9f-a352-a190c02b3005
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c8b08e9262c1fc251de9ce2e23ba37783e97ab9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="safegreaterthanequals"></a>SafeGreaterThanEquals
Сравнивает два числа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename T, typename U>  
inline bool SafeGreaterThanEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `t`  
 Первое число для сравнения. Это должен быть типа T.  
  
 [in] `u`  
 Второе число для сравнения. Это должен быть типа u.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` Если `t` больше или равно `u`; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 `SafeGreaterThanEquals` повышает оператор сравнения стандартных, так как он позволяет сравнить два различных типов чисел.  
  
 Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначена для операции сравнения одного без создания экземпляра [класс SafeInt](../windows/safeint-class.md).  
  
> [!NOTE]
>  Этот метод использовать только в том случае, когда один математической операции должны быть защищены. При наличии нескольких операций, следует использовать `SafeInt` класса вместо вызова автономного отдельных функций.  
  
 Дополнительные сведения о типах шаблонов T и U см. в разделе [функции SafeInt](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** Microsoft::Utilities  
  
## <a name="see-also"></a>См. также  
 [Функции SafeInt](../windows/safeint-functions.md)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [SafeInt-класс](../windows/safeint-class.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeLessThan](../windows/safelessthan.md)