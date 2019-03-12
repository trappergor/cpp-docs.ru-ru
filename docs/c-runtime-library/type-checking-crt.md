---
title: Проверка типов (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.types
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
ms.openlocfilehash: bb5aecc2b47aa8e88666f42d8022395bf99fd85e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747687"
---
# <a name="type-checking-crt"></a>Проверка типов (CRT)

Компилятор выполняет ограниченную проверку типов для функций, которые могут принимать переменное число аргументов, как указано ниже:

|Вызов функции |Аргументы, для которых проверяется тип|
|-------------------|-----------------------------|
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Первый аргумент (строка форматирования)|
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Первые два аргумента (файл или буфер и строка форматирования)|
|`_snprintf_s`|Первые три аргумента (файл или буфер, количество и строка форматирования)|
|`_open`|Первые два аргумента (путь и флаг `_open`)|
|`_sopen_s`|Первые три аргумента (путь, флаг `_open` и режим общего доступа)|
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Первые два аргумента (путь и первый указатель на аргумент)|
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Первые три аргумента (флаг режима, путь и первый указатель на аргумент)|

Компилятор выполняет такую же ограниченную проверку типов для аналогов этих функций для расширенных символов.

## <a name="see-also"></a>См. также

[Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)
