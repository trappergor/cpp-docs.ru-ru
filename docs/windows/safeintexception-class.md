---
title: Класс SafeIntException | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException Class
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a08db707afa2c307eab1dabdd0b20dad81e1a03e
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016344"
---
# <a name="safeintexception-class"></a>Класс SafeIntException
`SafeInt` Класс использует **SafeIntException** чтобы определить, почему не удается выполнить математическую операцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class SafeIntException;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
 [SafeIntException::SafeIntException](../windows/safeintexception-safeintexception.md)  
 Создает **SafeIntException** объекта.  
  
## <a name="remarks"></a>Примечания  
 [Класс SafeInt](../windows/safeint-class.md) является единственным классом, который использует **SafeIntException** класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [Класс SafeIntException](../windows/safeintexception-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** msl::utilities  
  
## <a name="see-also"></a>См. также  
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)