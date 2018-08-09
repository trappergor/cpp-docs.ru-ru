---
title: Оператор HString::Operator&lt; оператора | Документация Майкрософт
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
ms.openlocfilehash: 1bdc6d54a6c9b60036d7434edec960715db304e2
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017686"
---
# <a name="hstringoperatorlt-operator"></a>Оператор HString::Operator&lt; оператор
Указывает, является ли первый параметр меньше значения второго параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
```  
  
### <a name="parameters"></a>Параметры  
 *lhs*  
 Первый параметр для сравнения. *LHS* можно ссылаться на **HString**.  
  
 *правая часть*  
 Второй параметр для сравнения. *правая часть* можно ссылаться на **HString**.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если *lhs* параметр меньше, чем *rhs* параметра; в противном случае **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)