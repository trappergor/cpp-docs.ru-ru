---
title: stdin, stdout, stderr
ms.date: 10/23/2018
f1_keywords:
- stdin
- stderr
- stdout
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
ms.openlocfilehash: f9ed1f842bd174c2b926572856152cd69ade5a56
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328023"
---
# <a name="stdin-stdout-stderr"></a>stdin, stdout, stderr

## <a name="syntax"></a>Синтаксис

```
FILE *stdin;
FILE *stdout;
FILE *stderr;
#include <stdio.h>
```

## <a name="remarks"></a>Примечания

Это стандартные потоки для ввода, вывода и вывода ошибок.

По умолчанию стандартный ввод — чтение с клавиатуры, в то время как стандартный вывод и стандартный вывод ошибок печатаются на экране.

Следующие указатели потока доступны для получения стандартных потоков:

|Указатель|Поток|
|-------------|------------|
|`stdin`|Стандартный ввод|
|`stdout`|Стандартный вывод|
|`stderr`|Стандартная ошибка|

Эти указатели можно использовать в качестве аргументов для функций. Некоторые функции, например [getchar](../c-runtime-library/reference/getchar-getwchar.md) и [putchar](../c-runtime-library/reference/putchar-putwchar.md), используют `stdin` и `stdout` автоматически.

Эти указатели являются константами, и им не могут быть присвоены новые значения. Функцию [freopen](../c-runtime-library/reference/freopen-wfreopen.md) можно использовать, чтобы перенаправить потоки в файлы на диске или на другие устройства. Операционная система позволяет перенаправлять стандартный ввод и вывод программы на командном уровне.

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../c-runtime-library/stream-i-o.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
