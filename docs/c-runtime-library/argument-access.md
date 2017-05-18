---
title: "Доступ к аргументам | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.arguments
dev_langs:
- C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
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
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 66f9ff6dff86bbdff2ec86970a4176f3581316fa
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="argument-access"></a>Доступ к аргументам
Макросы `va_arg`, `va_end`, и `va_start` предоставляют доступ к аргументам функций, когда число аргументов является переменным. Эти макросы определяются в STDARG.H для совместимости с ANSI C и в VARARGS.H для совместимости с UNIX System V.  
  
### <a name="argument-access-macros"></a>Макросы для доступа к аргументам  
  
|Макрос|Применение|  
|-----------|-------------------------------|  
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Извлечение аргумента из списка|  
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Сброс указателя|  
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Установка указателя на начало списка аргументов|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
