---
title: SafeGreaterThan | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeGreaterThan
dev_langs:
- C++
helpviewer_keywords:
- SafeGreaterThan function
ms.assetid: 32cecac9-ba88-43eb-a7a4-30e390456739
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 098cc00d4b478df2be98bac6fc4a06990fe5aba0
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016041"
---
# <a name="safegreaterthan"></a>SafeGreaterThan
Сравнивает два числа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename T, typename U>  
inline bool SafeGreaterThan (  
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
 **значение true,** Если *t* больше, чем *u*; в противном случае **false**.  
  
## <a name="remarks"></a>Примечания  
 **SafeGreaterThan** расширяет оператор сравнения регулярного, используя для сравнения двух различных типов чисел.  
  
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
 [SafeLessThan](../windows/safelessthan.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)