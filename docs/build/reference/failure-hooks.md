---
title: Обработчики сбоев | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be598a77ca48eeee03360a3b598b0567abc6ee4b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="failure-hooks"></a>Обработчики сбоев
Обработчик сбоев включается так же, как [обработчика уведомлений](../../build/reference/notification-hooks.md). Процедура обработки требует возврата подходящего значения, чтобы обработки можно продолжить (HINSTANCE или FARPROC) или 0, чтобы указать, должно быть создано исключение.  
  
 Является переменной указателя, который ссылается на определяемую пользователем функцию:  
  
```  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 **DelayLoadInfo** структура содержит все соответствующие необходимые данные для точного отчета об ошибках, включая значение из `GetLastError`.  
  
 Если уведомление о **dliFailLoadLib**, функция обработчика может возвратить:  
  
-   0, если он не может обработать ошибку.  
  
-   HMODULE, когда обработчик сбоев устраняет проблему и загружает библиотеку.  
  
 Если уведомление о **dliFailGetProc**, функция обработчика может возвратить:  
  
-   0, если он не может обработать ошибку.  
  
-   Допустимый адрес процедуры (адрес функции импорта), когда обработчик сбоев успешно загружает адрес.  
  
## <a name="see-also"></a>См. также  
 [Обработка ошибок и предупреждений](../../build/reference/error-handling-and-notification.md)