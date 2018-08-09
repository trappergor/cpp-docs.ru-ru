---
title: SafeIntException::SafeIntException | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 393c424feb2a84fff85ba0efb5de7cbcaf54737c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016763"
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException
Создает **SafeIntException** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *кода*  
 Значение типа перечислимых данных, описывающее возникшую ошибку.  
  
## <a name="remarks"></a>Примечания  
 Возможные значения *кода* определены в файле Safeint.h. Для удобства возможные значения также перечислены здесь.  
  
-   `SafeIntNoError`  
  
-   `SafeIntArithmeticOverflow`  
  
-   `SafeIntDivideByZero`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** msl::utilities  
  
## <a name="see-also"></a>См. также  
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeIntException](../windows/safeintexception-class.md)   
 [Класс SafeInt](../windows/safeint-class.md)