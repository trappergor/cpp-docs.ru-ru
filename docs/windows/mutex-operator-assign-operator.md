---
title: "Mutex::operator =-оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs: C++
helpviewer_keywords: operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b7a9e35bb356d0f3ebfd870105c0b8217d7f658
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="mutexoperator-operator"></a>Оператор Mutex::operator=
Назначает (перемещается) указанный мьютекс объекта на текущий объект Mutex.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Mutex& operator=(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Ссылка rvalue на объект взаимного исключения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект Mutex.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе **семантику перемещения** раздел [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers
 
 ## <a name="see-also"></a>См. также
 [Класс Mutex](../windows/mutex-class1.md)