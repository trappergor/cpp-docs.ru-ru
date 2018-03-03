---
title: "Semaphore::operator =-оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7608c05c5915a3b4d04cf6a12e1b424e6b44ab4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="semaphoreoperator-operator"></a>Оператор Semaphore::operator=
Перемещает заданный дескриптор из объекта семафора для текущего объекта семафора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Semaphore& operator=(  
   _Inout_ Semaphore&& h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Ссылка rvalue на объект Semaphore.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект семафора.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers
 
 ## <a name="see-also"></a>См. также
 [Класс Semaphore](../windows/semaphore-class.md)