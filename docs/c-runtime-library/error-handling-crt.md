---
title: "Обработка ошибок (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.errors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка ошибок, процедуры С для"
  - "обработка ошибок, процедуры библиотеки"
  - "логические ошибки"
  - "проверка, для программных ошибок"
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Обработка ошибок (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти процедуры предназначены для обработки ошибок программы.  
  
### Процедуры обработки ошибок  
  
|Подпрограмма|Применение|Эквивалент в .NET Framework|  
|------------------|----------------|---------------------------------|  
|макрос [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Тестирование ошибок программной логики; доступен в версиях отладки и выпуска библиотеки времени выполнения|[\<caps:sentence id\="tgt8" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|Макросы [\_ASSERT, \_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)|Аналогичны `assert`, но доступны только в версиях отладки библиотеки времени выполнения|[\<caps:sentence id\="tgt11" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|Сбрасывает индикатор ошибки.  Вызов `rewind` или закрытие потока также сбрасывает индикатор ошибки.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_eof](../c-runtime-library/reference/eof.md)|Проверка наличия конца файла в низкоуровневом вводе\-выводе|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[feof](../c-runtime-library/reference/feof.md)|Проверка наличия конца файла.  Признаком конца файла также является случай, когда `_read`  возвращает 0.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[ferror](../c-runtime-library/reference/ferror.md)|Проверка ошибок поточного ввода\-вывода|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|макросы [\_RPT, \_RPTF](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md)|Создают отчет аналогично `printf`, но доступны только в версиях отладки библиотеки времени выполнения|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_set\_error\_mode](../c-runtime-library/reference/set-error-mode.md)|Изменяет `__error_mode` для указания расположения не по умолчанию, где среда выполнения C записывает сообщение об ошибке для ошибок, которые могут вызвать завершение программы.||  
|[\_set\_purecall\_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Задает обработчик для вызова чисто виртуальной функции.||  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)