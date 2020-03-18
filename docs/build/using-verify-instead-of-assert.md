---
title: Использование VERIFY вместо ASSERT
ms.date: 05/06/2019
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
ms.openlocfilehash: bfc0847677ae232fef67ab6200c626472f042bdb
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438619"
---
# <a name="using-verify-instead-of-assert"></a>Использование VERIFY вместо ASSERT

Предположим, что при запуске отладочной версии приложения MFC проблемы не возникают. Однако окончательная версия одного и того же приложения завершается сбоем, возвращает неверные результаты и/или ведет к ненормальному поведению.

Эта проблема может возникать при помещении важного кода в оператор ASSERT, чтобы убедиться, что он выполняется правильно. Поскольку инструкции ASSERT записываются в комментарий в сборке выпуска программы MFC, код не выполняется в сборке выпуска.

Если вы используете ASSERT для подтверждения успешности вызова функции, рассмотрите возможность использования оператора [Verify](../mfc/reference/diagnostic-services.md#verify) . Макрос VERIFY оценивает собственные аргументы в сборках отладки и выпуска приложения.

Другая рекомендуемая методика — назначение возвращаемого значения функции временной переменной, а затем проверка переменной в операторе ASSERT.

Изучите следующий фрагмент кода:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Этот код прекрасно работает в отладочной версии приложения MFC. В случае сбоя вызова `calloc( )` появляется диагностическое сообщение, включающее файл и номер строки. Однако в розничной сборке приложения MFC:

- вызов `calloc( )` никогда не происходит, при этом `buf` не инициализирована или

- `strcpy_s( )` копирует "`Hello, World`" в случайную часть памяти, что может привести к сбою приложения или вызвать зависание системы, или

- `free()` пытается освободить память, которая никогда не была выделена.

Чтобы правильно использовать ASSERT, образец кода должен быть изменен следующим образом:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );
ASSERT( buf != NULL );
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Вместо этого можно использовать команду VERIFY:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

## <a name="see-also"></a>См. также раздел

[Устранение проблем сборки выпуска](fixing-release-build-problems.md)
