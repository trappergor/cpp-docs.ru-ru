---
title: __argc, __argv, __wargv
description: Описание глобальных констант библиотеки времени выполнения Microsoft C __argc , __argv и __wargv .
ms.date: 11/04/2016
api_name:
- __wargv
- __argv
- __argc
api_location:
- msvcrt120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __argv
- __argc
- __wargv
helpviewer_keywords:
- __argv
- __wargv
- __argc
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
no-loc:
- __argc
- __argv
- __wargv
- main
- wmain
ms.openlocfilehash: 02c130be0d2dcb8e48d2bb5c75438c94003fc9dd
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507590"
---
# <a name="no-loc__argc-no-loc__argv-no-loc__wargv"></a>__argc, __argv, __wargv

Глобальная переменная `__argc` — это счетчик числа аргументов командной строки, переданных программе. `__argv` — указатель на массив одно- или многобайтовых строк, который содержит аргументы программы, а `__wargv` — указатель на массив строк расширенных символов, который содержит аргументы программы. Эти глобальные переменные обеспечивают аргументы для `main` или `wmain`.

## <a name="syntax"></a>Синтаксис

```C
extern int __argc;
extern char ** __argv;
extern wchar_t ** __wargv;
```

## <a name="remarks"></a>Remarks

В программе, которая использует функцию `main`, `__argc` и `__argv` инициализируются при запуске программы на основе командной строки, которая используется для запуска программы. Командная строка разбирается на отдельные аргументы, а подстановочные знаки разворачиваются. Число аргументов назначается функции `__argc`, строки аргументов выделяются в куче, а указатель на массив аргументов назначается `__argv`. В программе, которая скомпилирована для использования расширенных символов и функции `wmain`, аргументы анализируются и подстановочные знаки разворачиваются как строки расширенных символов, а указатель на массив строк аргументов назначается `__wargv`.

Для создания переносимого кода рекомендуется использовать аргументы, переданные в `main`, чтобы получить аргументы командной строки в программе.

### <a name="generic-text-routine-mappings"></a>Сопоставления универсальных текстовых подпрограмм

|Процедура Tchar.h|_UNICODE не определен|_UNICODE определено|
|---------------------|---------------------------|-----------------------|
|`__targv`|`__argv`|`__wargv`|

## <a name="requirements"></a>Требования

|Глобальная переменная|Обязательный заголовок|
|---------------------|---------------------|
|`__argc`, `__argv`, `__wargv`|\<stdlib.h>, \<cstdlib> (C++)|

`__argc`, `__argv` и `__wargv` являются расширениями Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Глобальные переменные](../c-runtime-library/global-variables.md)\
[main аргументы функции и командной строки (C++)](../cpp/main-function-command-line-args.md)\
[Использование wmain вместо main](../cpp/main-function-command-line-args.md)
