---
title: "HString::Operator ==-оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
dev_langs:
- C++
ms.assetid: 77ff4c1a-e62a-4256-bf9d-0f017137c630
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6db6c449a7ceb4799feb4740c11385875a6309ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="hstringoperator-operator"></a>Оператор HString::Operator==
Указывает, равны ли два параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline bool operator==(  
               const HString& lhs,   
               const HString& rhs) throw()  
  
inline bool operator==(  
                const HString& lhs,   
                const HStringReference& rhs) throw()  
  
inline bool operator==(  
                const HStringReference& lhs,   
                const HString& rhs) throw()  
  
inline bool operator==(  
                 const HSTRING& lhs,   
                 const HString& rhs) throw()  
  
inline bool operator==(  
                 const HString& lhs,   
                 const HSTRING& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый параметр для сравнения. `lhs`может быть объект HString или HStringReference или дескриптор HSTRING.  
  
 `rhs`  
 Второй параметр для сравнения.`rhs` может быть объект HString или HStringReference или дескриптор HSTRING.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`Если `lhs` и `rhs` параметры равны; в противном случае — `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)