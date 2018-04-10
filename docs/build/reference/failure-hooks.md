---
title: Обработчики сбоев | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1609b713fef253e8beab270ee2ed048466da6504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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