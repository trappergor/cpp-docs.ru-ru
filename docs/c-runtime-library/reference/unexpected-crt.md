---
title: "unexpected (CRT) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- unexpected
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- unexpected
dev_langs:
- C++
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 33cebdc6982d1f91f4a6766776347f6c3cb89f3e
ms.lasthandoff: 02/24/2017

---
# <a name="unexpected-crt"></a>unexpected (CRT)
Вызывает функцию `terminate` или функцию, заданную с помощью функции `set_unexpected`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void unexpected( void );  
```  
  
## <a name="remarks"></a>Примечания  
 Подпрограмма `unexpected` не используется в текущей реализации обработки исключений C++. По умолчанию `unexpected` вызывает функцию `terminate`. Можно изменить это поведение по умолчанию, создав пользовательскую функцию завершения и вызвав функцию `set_unexpected` с именем этой функции в качестве аргумента. `unexpected` вызывает последнюю функцию, заданную в качестве аргумента для функции `set_unexpected`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`unexpected`|\<eh.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 [Класс System::Exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx)  
  
## <a name="see-also"></a>См. также  
 [Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)
