---
title: Использование VERIFY вместо ASSERT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- assert
dev_langs:
- C++
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea6ea90460f3fd28724ee1fd34dfdeb3f6ae80b2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711780"
---
# <a name="using-verify-instead-of-assert"></a>Использование VERIFY вместо ASSERT

Предположим, что при запуске отладочной версии приложения MFC, нет никаких проблем. Тем не менее версии того же приложения аварийно завершает работу, возвращает неверные результаты, и (или) демонстрирует некоторые Аномальное поведение.

Эта проблема может возникать при размещении важные кода с помощью оператора ASSERT, чтобы убедиться, что он выполняет правильно. Поскольку операторы ASSERT закомментированы в окончательной сборке приложения MFC, код не выполняется в окончательной сборке.

Если вы используете ASSERT на подтверждение вызов функции, рассмотрите возможность использования [VERIFY](../../mfc/reference/diagnostic-services.md#verify) вместо этого. VERIFY-макрос оценивает свои аргументы в обоих отладочные и окончательные сборки приложения.

Другой рекомендуется назначить возвращаемое значение функции во временную переменную и затем проверить переменную в операторе ASSERT.

Рассмотрим следующий фрагмент кода:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Этот код корректно работает в отладочной версии приложения MFC. Если вызов `calloc( )` завершается ошибкой, откроется диагностическое сообщение, включающий имя файла и номер строки. Тем не менее в окончательной сборке приложения MFC:

- вызов `calloc( )` никогда не происходит, оставляя `buf` не инициализирована, или

- `strcpy_s( )` Копирует "`Hello, World`" в произвольный участок памяти, сбой в приложении или чего система перестает отвечать на запросы, или

- `free()` пытается освободить память, которая не была выделена.

Для правильного использования ASSERT, в образце кода необходимо заменить следующее:

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

Или можно использовать вместо этого ПРОВЕРЬТЕ:

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

[Устранение проблем сборки выпуска](../../build/reference/fixing-release-build-problems.md)