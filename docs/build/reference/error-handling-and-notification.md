---
title: "Обработка ошибок и предупреждений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 738721eb3fc37ba076157129cb88a22f2c90e464
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="error-handling-and-notification"></a>Обработка ошибок и предупреждений
Дополнительные сведения об обработке ошибок и предупреждений см. в разделе [понятие вспомогательной функции](understanding-the-helper-function.md).  
  
 Дополнительные сведения для функций-ловушек см. в разделе [определение структуры и константы](../../build/reference/structure-and-constant-definitions.md).  
  
 Если программа использует DLLs, загружаемых с задержкой, она должна обрабатывать ошибки надежно после сбоев, возникающих во время выполнения программы приведет к включению необработанных исключений. Обработка сбоев состоит из двух частей:  
  
 Восстановление ловушки.  
 Если код должен либо предоставить альтернативный библиотеки и/или подпрограмму при сбое, ловушка может быть предоставлена вспомогательную функцию, которая поддерживает или исправить ситуацию. Процедура обработки требует возврата подходящего значения, так что обработки можно продолжить (HINSTANCE или FARPROC) или 0, чтобы указать, должно быть создано исключение. Он также может вызывать собственное исключение или **longjmp** за пределы ловушки. Существуют обработчики уведомления и обработчики сбоев.  
  
 Отчет или исключение.  
 Если все необходимое для обработки ошибки прекращение процедуры, никаких обработчиков не требуется до тех пор, пока код пользователя может обработать исключение.  
  
 Обработка ошибок и предупреждений, рассматриваются в следующих разделах:  
  
-   [Обработчики уведомлений](../../build/reference/notification-hooks.md)  
  
-   [Обработчики сбоев](../../build/reference/failure-hooks.md)  
  
-   [Исключения](../../build/reference/exceptions-c-cpp.md)  
  
## <a name="see-also"></a>См. также  
 [Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)