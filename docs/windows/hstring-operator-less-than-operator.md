---
title: HString::Operator&lt; оператор | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs:
- C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8fae7195f048cd680be513bd54b635e2e1e9bbf7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="hstringoperatorlt-operator"></a>HString::Operator&lt; оператор
Указывает, является ли первый параметр меньше второго параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый параметр для сравнения. `lhs` может быть ссылкой на HString.  
  
 `rhs`  
 Второй параметр для сравнения. `rhs` может быть ссылкой на HString.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` Если `lhs` параметр меньше, чем `rhs` параметр; в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)