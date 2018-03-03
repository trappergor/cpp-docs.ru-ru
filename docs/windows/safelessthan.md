---
title: "SafeLessThan | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeLessThan
dev_langs:
- C++
helpviewer_keywords:
- SafeLessThan function
ms.assetid: 9d85bc0d-8d94-4d59-9b72-ef3c63a120a0
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c490f02f6c27d517095ab3f75a31bb03fe14f63
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="safelessthan"></a>SafeLessThan
Определяет, является ли одно число меньше другого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T, typename U>  
inline bool SafeLessThan (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `t`  
 Первое число. Это должен быть типа T.  
  
 [in] `u`  
 Второй номер. Это должен быть типа u.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`Если `t` — меньше, чем `u`; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод расширяет возможности оператор сравнения стандартной, так как `SafeLessThan` позволяет сравнить два различных типа номер.  
  
 Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначена для операции сравнения одного без создания экземпляра [класс SafeInt](../windows/safeint-class.md).  
  
> [!NOTE]
>  Этот метод использовать только в том случае, когда один математической операции должны быть защищены. При наличии нескольких операций, следует использовать `SafeInt` класса, вместо того чтобы вызывать отдельные функции автономный.  
  
 Дополнительные сведения о типах шаблонов T и U см. в разделе [функции SafeInt](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** Microsoft::Utilities  
  
## <a name="see-also"></a>См. также  
 [Функции SafeInt](../windows/safeint-functions.md)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [SafeInt-класс](../windows/safeint-class.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)