---
title: "Безопасные перегрузки шаблонов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES
- _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT
dev_langs:
- C++
helpviewer_keywords:
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES
- _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT
- secure template overloads
ms.assetid: 562741d0-39c0-485e-8529-73d740f29f8f
caps.latest.revision: 13
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 1519fde9f60f9cb9b45db4a4921f2bec5185e549
ms.lasthandoff: 02/24/2017

---
# <a name="secure-template-overloads"></a>Безопасные перегрузки шаблонов
Многие функции CRT стали нерекомендуемыми в пользу новых более безопасных версий (например, `strcpy_s` является более безопасной заменой для `strcpy`). CRT предоставляет перегруженные шаблоны, которые помогают упростить переход к более безопасным вариантам.  
  
 Например, этот код создает предупреждение, поскольку функция `strcpy` стала нерекомендуемой:  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // warning: deprecated`  
  
 Это предупреждение можно игнорировать. Определите символ `_CRT_SECURE_NO_WARNINGS`, чтобы отключить предупреждение, или обновите код для использования функции `strcpy_s`:  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, 10, "test"); // security-enhanced _s function`  
  
 Перегруженные версии шаблонов предоставляют дополнительные возможности. Определение `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` как значения "1" включает использование перегруженных шаблонов стандартных функций CRT, вызывающих более безопасные варианты автоматически. Если `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` определен как значение "1", никаких изменений в коде не требуется. Вызов функции `strcpy` будет в фоновом режиме заменен вызовом функции `strcpy_s` с автоматически предоставленным аргументом размера.  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` не влияет на функции, которые принимают количество, например `strncpy`. Чтобы включить перегруженные шаблоны для функций, принимающих количество, определите `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` как значение "1". Однако перед этим действием следует убедиться, что код передает количество символов, а не размер буфера (частая ошибка). Кроме того, код, который явно записывает значение NULL в конец буфера после вызова функции, является необязательным, если вызывается безопасный вариант. Если требуется поведение усечения см. документацию [_TRUNCATE](../c-runtime-library/truncate.md).  
  
> [!NOTE]
>  Макрос `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` требует, чтобы `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` также был определен как значение "1". Если `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` определен как значение "1" и `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` определен как значение "0", в приложении не выполняются никакие перегрузки шаблонов.  
  
 Определение `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` как значения "1" включает перегрузки шаблонов безопасных вариантов (имена оканчиваются на "_s"). В этом случае, если `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` определен как значение "1", в исходном коде необходимо сделать одно небольшое изменение.  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 Требуется изменить только имена функций (путем добавления "_s"); перегрузка шаблона предоставит аргумент размера.  
  
 По умолчанию `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` и `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` определены как "0" (запрещено), а `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` определен как "1" (разрешено).  
  
 Обратите внимание, что эти перегрузки шаблонов работают только для статических массивов. Динамически выделенные буферы требуют дополнительных изменений исходного кода. В приведенных выше примерах:  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy(szBuf, "test"); // still deprecated; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
 А также:  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy_s(szBuf, "test"); // doesn't compile; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
## <a name="see-also"></a>См. также  
 [Функции безопасности в CRT](../c-runtime-library/security-features-in-the-crt.md)   
 [Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)
