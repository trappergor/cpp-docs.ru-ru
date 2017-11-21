---
title: "HStringReference::Operator&lt; оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs: C++
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 46d839cd10144877ee4af561ce9e1ab52343de83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreferenceoperatorlt-operator"></a>HStringReference::Operator&lt; оператор
Указывает, является ли первый параметр меньше второго параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
```  
  
#### <a name="parameters"></a>Параметры  
 `lhs`  
 Первый параметр для сравнения. `lhs`может быть ссылкой на HStringReference.  
  
 `rhs`  
 Второй параметр для сравнения.  `rhs`может быть ссылкой на HStringReference.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`Если `lhs` параметр меньше, чем `rhs` параметр; в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)