---
title: "Класс Platform::ObjectDisposedException | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ObjectDisposedException
- VCCORLIB/Platform::ObjectDisposedException::ObjectDisposedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::ObjectDisposedException
ms.assetid: 68506fe4-d09c-4407-999f-1e3edb261d41
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52732d37179a12ebe8470380570e3cf51965d9c6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="platformobjectdisposedexception-class"></a>Класс Platform::ObjectDisposedException
Вызывается при выполнении операции над ликвидированным объектом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class ObjectDisposedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md).  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## <a name="see-also"></a>См. также  
 [Класс Platform::COMException](../cppcx/platform-comexception-class.md)