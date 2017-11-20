---
title: "Класс Platform::AccessDeniedException | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
dev_langs: C++
helpviewer_keywords: Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 87e94e5f0aafabe8d3c8f4cb549a80717cf82742
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="platformaccessdeniedexception-class"></a>Класс Platform::AccessDeniedException
Возникает при запрете доступа к ресурсу или функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable  
```  
  
### <a name="remarks"></a>Примечания  
 Если возникло это исключение, проверьте, что вы запросили соответствующую возможность и указали необходимые объявления в манифесте пакета приложения. Дополнительные сведения см. в статье [COMException](../cppcx/platform-comexception-class.md) .  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## <a name="see-also"></a>См. также  
 [Класс Platform::COMException](../cppcx/platform-comexception-class.md)