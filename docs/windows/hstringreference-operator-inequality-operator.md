---
title: "HStringReference::Operator! =-оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
dev_langs: C++
ms.assetid: 01ab6691-1fc7-4feb-85f0-fe795593a160
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3c55b115c0a0d02df7cebbb9c91a828afcb6c81e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreferenceoperator-operator"></a>Оператор HStringReference::O
Указывает, равны ли два параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый параметр для сравнения. `lhs`может быть объект HStringReference или дескриптор HSTRING.  
  
 `rhs`  
 Второй параметр для сравнения.  `rhs`может быть объект HStringReference или дескриптор HSTRING.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`Если `lhs` и `rhs` параметров не равны; в противном случае — `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)