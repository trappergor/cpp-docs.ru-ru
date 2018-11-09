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
ms.openlocfilehash: fd892426bb7301acad7ce2a93430e52f25e7c9b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626115"
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