---
title: "Обработка ошибок (CRT) | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.errors
dev_langs:
- C++
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: 8
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
ms.openlocfilehash: ab0f6998aa2f4f6ba5066cbc1d4c6813dcbaab0b
ms.lasthandoff: 02/24/2017

---
# <a name="error-handling-crt"></a>Обработка ошибок (CRT)
Используйте эти подпрограммы для обработки ошибок в программах.  
  
### <a name="error-handling-routines"></a>Подпрограммы для обработки ошибок  
  
|Подпрограмма|Применение|Эквивалент .NET Framework|  
|-------------|---------|-------------------------------|  
|Макрос [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Проверка на наличие ошибок в логике программы; доступен как в итоговой, и в отладочной версии библиотек среды выполнения.|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|Макросы [_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Подобен `assert`, но доступен только в отладочных версиях библиотеки среды выполнения.|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|Сброс индикатора ошибки. Вызов `rewind` или закрытие потока также приводит к сбросу индикатора ошибки.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_eof](../c-runtime-library/reference/eof.md)|Поиск конца файла в низкоуровневых операциях ввода-вывода|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[feof](../c-runtime-library/reference/feof.md)|Проверка на наличие конца файла. Конец файла также указан, если `_read` возвращает результат 0.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[ferror](../c-runtime-library/reference/ferror.md)|Проверка на наличие ошибок потокового ввода-вывода|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|Макросы [_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Создают отчет, подобный `printf`, но доступны только в отладочных версиях библиотеки среды выполнения.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Изменяет `__error_mode` для определения отличного от используемого по умолчанию расположения, куда среда выполнения C записывает сообщение об ошибке для ошибок, которые могут вызвать завершение программы.||  
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Задает обработчик для вызова чистой виртуальной функции.||  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
