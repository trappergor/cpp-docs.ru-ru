---
title: "HStringReference::Operator ==-оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
dev_langs: C++
ms.assetid: cad3d52d-cd67-4194-a270-5239b1121a09
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 630a10fe751593736fef39d2ca9ba8a56c1d5bed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreferenceoperator-operator"></a>Оператор HStringReference::Operator==
Указывает, равны ли два параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline bool operator==(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый параметр для сравнения. `lhs`может быть объект HStringReference или дескриптор HSTRING.  
  
 `rhs`  
 Второй параметр для сравнения.  `rhs`может быть объект HStringReference или дескриптор HSTRING.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`Если `lhs` и `rhs` параметры равны; в противном случае — `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)