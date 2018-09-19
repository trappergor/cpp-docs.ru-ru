---
title: Функция make_exception_ptr | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ppltasks/std::make_exception_ptr
dev_langs:
- C++
ms.assetid: 8d81cf7a-818e-4b27-8d49-440ec3088609
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3f483d266b8150dfd4aaa5299ffec280d447157
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037623"
---
# <a name="makeexceptionptr-function"></a>Функция make_exception_ptr
## <a name="syntax"></a>Синтаксис  
  
```
template<class _E>
exception_ptr make_exception_ptr(_E _Except);
```  
  
#### <a name="parameters"></a>Параметры  
*_E*<br/>
Тип исключения.

*_Except.*<br/>
Значение исключения.
  
## <a name="return-value"></a>Возвращаемое значение  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Пространство имен std](std-namespace.md)
