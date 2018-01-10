---
title: "Доступ к аргументам | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.arguments
dev_langs: C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97db036822687936f3f8e4084c065c8ec64ca23e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="argument-access"></a>Доступ к аргументам
Макросы `va_arg`, `va_end`, и `va_start` предоставляют доступ к аргументам функций, когда число аргументов является переменным. Эти макросы определяются в STDARG.H для совместимости с ANSI C и в VARARGS.H для совместимости с UNIX System V.  
  
### <a name="argument-access-macros"></a>Макросы для доступа к аргументам  
  
|Макрос|Использовать|  
|-----------|-------------------------------|  
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Извлечение аргумента из списка|  
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Сброс указателя|  
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Установка указателя на начало списка аргументов|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)