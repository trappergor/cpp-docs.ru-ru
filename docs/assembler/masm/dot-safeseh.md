---
title: . SAFESEH | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ea34448b4dae0525e7feb2fd7cca310a95a6e3c
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="safeseh"></a>.SAFESEH
Регистрирует функцию как структурированного обработчика исключений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
.SAFESEH identifier  
```  
  
## <a name="remarks"></a>Примечания  
 *Идентификатор* должен быть Идентификатором для локально определенная [PROC](../../assembler/masm/proc.md) или [EXTRN](../../assembler/masm/extrn.md) коде Объект [МЕТКА](../../assembler/masm/label-masm.md) не допускается. . Требуется директива SAFESEH [/SAFESEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe параметр командной строки.  
  
 Дополнительные сведения об обработчиках структурированных исключений см. в разделе [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).  
  
 Например регистрация обработчика безопасных исключений, создайте новый файл MASM (как показано ниже), объединить с/SAFESEH и добавить его к связанным объектам.  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)