---
title: "Класс SafeIntException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeIntException Class
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 91f1c80273d0e1ed41ea86774c71fcbe8ad1bbf6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="safeintexception-class"></a>Класс SafeIntException
`SafeInt` Класс использует `SafeIntException` чтобы определить, почему математические операции невозможно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class SafeIntException;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
 [SafeIntException::SafeIntException](../windows/safeintexception-safeintexception.md)  
 Создает объект `SafeIntException`.  
  
## <a name="remarks"></a>Примечания  
 [Класс SafeInt](../windows/safeint-class.md) является единственным классом, который использует `SafeIntException` класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [Класс SafeIntException](../windows/safeintexception-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** msl::utilities  
  
## <a name="see-also"></a>См. также  
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)