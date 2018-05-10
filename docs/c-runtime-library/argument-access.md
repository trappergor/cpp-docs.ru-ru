---
title: Доступ к аргументам | Документы Майкрософт
ms.custom: ''
ms.date: 04/04/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.arguments
dev_langs:
- C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38d4031fcfba793a99688b6fd1cc91a3f1519989
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="argument-access"></a>Доступ к аргументам

Макросы **va_arg**, **va_end** и **va_start** предоставляют доступ к аргументам функций, когда число аргументов является переменным. Эти макросы определяются в \<stdarg.h> для совместимости с C ANSI/ISO и в \<varargs.h> для совместимости с UNIX System V.

## <a name="argument-access-macros"></a>Макросы для доступа к аргументам

|Макрос|Использовать|
|-----------|-------------------------------|
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Извлечение аргумента из списка|
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Сброс указателя|
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Установка указателя на начало списка аргументов|

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)
