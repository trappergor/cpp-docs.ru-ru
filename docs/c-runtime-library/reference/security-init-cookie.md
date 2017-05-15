---
title: "__security_init_cookie | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __security_init_cookie
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
- security_init_cookie
- __security_init_cookie
dev_langs:
- C++
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6c1bf74e3b597026af02e2fdd4dc6cec327793dd
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="securityinitcookie"></a>__security_init_cookie
Инициализирует глобальный cookie-файл безопасности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __security_init_cookie(void);  
```  
  
## <a name="remarks"></a>Примечания  
 Глобальный cookie-файл безопасности используется для защиты от переполнения буфера в коде, скомпилированном с параметром [/GS (проверка безопасности буфера)](../../build/reference/gs-buffer-security-check.md), и в коде, в котором используется структурная обработка исключений. При входе в функцию с защитой от переполнения cookie-файл помещается в стек, а при выходе значение в стеке сравнивается с глобальным cookie-файлом. Любое различие между ними указывает, что произошло переполнение буфера, что приводит к немедленному завершению работы программы.  
  
 Обычно CRT вызывает `__security_init_cookie` при инициализации. Если пропустить инициализацию CRT, например если используется [/ENTRY](../../build/reference/entry-entry-point-symbol.md) для указания точки ввода, то нужно вызвать `__security_init_cookie` вручную. Если не вызвать `__security_init_cookie`, то для глобального cookie-файла безопасности устанавливается значение по умолчанию и нарушается защита от переполнения буфера. Злоумышленник может воспользоваться этим значением cookie-файла по умолчанию, чтобы обойти проверку переполнения буфера, поэтому рекомендуется всегда вызывать `__security_init_cookie` при определении собственной точки входа.  
  
 Функцию `__security_init_cookie` необходимо вызывать до входа в любую функцию, защищенную от переполнения; в противном случае будет обнаружено ложное переполнение буфера. Подробнее: [Ошибка R6035 времени выполнения C](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## <a name="example"></a>Пример  
 Примеры см. в разделе [Ошибка R6035 времени выполнения C](../../error-messages/tool-errors/c-runtime-error-r6035.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`__security_init_cookie`|\<process.h>|  
  
 `__security_init_cookie` — расширение Майкрософт для стандартной библиотеки выполнения C. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Комплексные проверки безопасности компилятора](http://go.microsoft.com/fwlink/?linkid=7260)
