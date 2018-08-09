---
title: SafeAdd | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeAdd
dev_langs:
- C++
helpviewer_keywords:
- SafeAdd function
ms.assetid: 3f82b91d-59fe-4ee1-873b-d056182fa8be
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ff51780cc05a4c133975d95dc89455a90e717d1
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014618"
---
# <a name="safeadd"></a>SafeAdd
Складывает два числа способом, который обеспечивает защиту от переполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename T, typename U>  
inline bool SafeAdd (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *t*  
 Первое число для добавления. Это должен быть типа T.  
  
 [in] *u*  
 Второе число для добавления. Это должен быть типа u.  
  
 [out] *результат*  
 Параметр где **SafeAdd** сохраняет результат.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** при отсутствии ошибок; **false** при возникновении ошибки.  
  
## <a name="remarks"></a>Примечания  
 Этот метод является частью [библиотека SafeInt](../windows/safeint-library.md) и предназначен для операции одно добавление без создания экземпляра [класс SafeInt](../windows/safeint-class.md).  
  
> [!NOTE]
>  Этот метод должен использоваться только в тех случаях, когда одной математической операции должны быть защищены. При наличии нескольких операций, следует использовать `SafeInt` класса вместо вызова отдельных автономных функций.  
  
 Дополнительные сведения о типах шаблонов T и U см. в разделе [функции SafeInt](../windows/safeint-functions.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** Microsoft::Utilities  
  
## <a name="see-also"></a>См. также  
 [Функции SafeInt](../windows/safeint-functions.md)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)   
 [SafeSubtract](../windows/safesubtract.md)