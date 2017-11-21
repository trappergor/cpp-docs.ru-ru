---
title: "HStringReference::Operator =-оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs: C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b6a9938308f0cbd8339c24d1876c09ae49df349
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreferenceoperator-operator"></a>Оператор HStringReference::Operator=
Значение другой объект HStringReference перемещается в текущий объект HStringReference.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### <a name="parameters"></a>Параметры  
 `other`  
 Существующий объект HStringReference.  
  
## <a name="remarks"></a>Примечания  
 Значение существующего объекта `other` копируется в текущий объект HStringReference, а затем объект `other` удаляется.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)