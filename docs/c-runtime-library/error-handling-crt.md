---
title: "Обработка ошибок (CRT) | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.errors
dev_langs: C++
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f40b2deb5c78667e5343bd2be0948252e2f2e154
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="error-handling-crt"></a>Обработка ошибок (CRT)
Используйте эти подпрограммы для обработки ошибок в программах.  
  
### <a name="error-handling-routines"></a>Подпрограммы для обработки ошибок  
  
|Подпрограмма|Использовать|  
|-------------|---------|  
|Макрос [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Проверка на наличие ошибок в логике программы; доступен как в итоговой, так и в отладочной версии библиотек среды выполнения.|  
|Макросы [_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Подобен `assert`, но доступен только в отладочных версиях библиотеки среды выполнения.|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|Сброс индикатора ошибки. Вызов `rewind` или закрытие потока также приводит к сбросу индикатора ошибки.|  
|[_eof](../c-runtime-library/reference/eof.md)|Поиск конца файла в низкоуровневых операциях ввода-вывода.|  
|[feof](../c-runtime-library/reference/feof.md)|Проверка на наличие конца файла. Конец файла также указан, если `_read` возвращает результат 0.|  
|[ferror](../c-runtime-library/reference/ferror.md)|Проверка на наличие ошибок потокового ввода-вывода.|  
|Макросы [_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|Создают отчет, подобный `printf`, но доступны только в отладочных версиях библиотеки среды выполнения.|  
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Изменяет `__error_mode` для определения отличного от используемого по умолчанию расположения, куда среда выполнения C записывает сообщение об ошибке для ошибок, которые могут вызвать завершение программы.|  
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Задает обработчик для вызова чистой виртуальной функции.|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)