---
title: "Класс Platform::FailureException | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::FailureException::FailureException
- VCCORLIB/Platform::FailureException
dev_langs: C++
helpviewer_keywords: Platform::FailureException
ms.assetid: 1729cd07-bfc2-448e-9db5-185d5cbf5b81
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 441c8893015bb2f2a961c83b129af8f03dd527df
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="platformfailureexception-class"></a>Класс Platform::FailureException
Вызывается, если операция вызвала сбой. Эквивалентно E_FAIL HRESULT.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class FailureException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в описании класса [COMException](../cppcx/platform-comexception-class.md) .  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## <a name="see-also"></a>См. также  
 [Класс Platform::COMException](../cppcx/platform-comexception-class.md)