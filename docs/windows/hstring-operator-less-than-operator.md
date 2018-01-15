---
title: "HString::Operator&lt; оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs: C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4cbb21e34255d5350702d949792656bdf0a849a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 Первый параметр для сравнения. `lhs`может быть ссылкой на HString.  
  
 `rhs`  
 Второй параметр для сравнения. `rhs`может быть ссылкой на HString.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`Если `lhs` параметр меньше, чем `rhs` параметр; в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)