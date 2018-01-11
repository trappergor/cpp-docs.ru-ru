---
title: "Класс Platform::ObjectDisposedException | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::ObjectDisposedException
- VCCORLIB/Platform::ObjectDisposedException::ObjectDisposedException
dev_langs: C++
helpviewer_keywords: Platform::ObjectDisposedException
ms.assetid: 68506fe4-d09c-4407-999f-1e3edb261d41
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8751940669dd947de8b4dd789aad3e739dd412bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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