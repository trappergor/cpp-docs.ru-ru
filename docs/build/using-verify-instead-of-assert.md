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
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438619"
---
# <a name="using-verify-instead-of-assert"></a>Использование VERIFY вместо ASSERT

Предположим, что отладочная версия приложения MFC выполняется без проблем. Однако версия выпуска того же приложения завершается аварийно, возвращает неверные результаты и (или) демонстрирует аномальное поведение.

Такая ситуация может возникать, когда вы помещаете важный код в оператор ASSERT, чтобы проверить правильность его выполнения. Так как операторы ASSERT в сборке выпуска программы MFC закомментированы, этот код в сборке выпуска не выполняется.

Если вы с помощью оператора ASSERT проверяете успешность вызова функции, попробуйте вместо него использовать [VERIFY](../mfc/reference/diagnostic-services.md#verify). Макрос VERIFY оценивает собственные аргументы как в сборке отладки, так и в сборке выпуска приложения.

Другой рекомендуемый способ — назначение возвращаемого значения функции временной переменной, а затем проверка этой переменной в операторе ASSERT.

Рассмотрим следующий фрагмент кода.

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Этот код прекрасно работает в отладочной версии приложения MFC. В случае сбоя вызова `calloc( )` появляется диагностическое сообщение, в котором указан файл и номер строки. Однако в окончательной сборке приложения MFC:

- вызов `calloc( )` никогда не происходит, при этом `buf` не инициализируется, или

- `strcpy_s( )` копирует "`Hello, World`" в случайный фрагмент памяти, что может привести к сбою приложения или зависанию системы, или

- `free()` пытается освободить память, которая никогда не была выделена.

Чтобы правильно использовать ASSERT, необходимо изменить пример кода следующим образом:

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

Можно также вместо ASSERT использовать VERIFY:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

## <a name="see-also"></a>См. также

[Устранение проблем сборки выпуска](fixing-release-build-problems.md)
