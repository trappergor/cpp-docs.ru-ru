---
title: Создание встроенных текстовых стилей
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
ms.openlocfilehash: 4989d0757e893a7bc4b0a0e8937afee18719aa4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523119"
---
# <a name="creating-inline-file-text"></a>Создание встроенных текстовых стилей

Встроенные файлы являются временным или постоянным.

## <a name="syntax"></a>Синтаксис

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Примечания

Укажите *inlinetext* в первой строке после команды. Обозначения конца с двойные угловые скобки (<<) в начале отдельной строке. Файл содержит все *inlinetext* перед разделяющими скобками. *Inlinetext* может иметь расширения макросов и замены, но не директивы или комментарии makefile. Пробелы, знаки табуляции и символы новой строки обрабатываются буквально.

Временный файл существует в течение сеанса и могут быть использованы другими командами. Укажите **Сохранить** после закрывающие угловые скобки, чтобы сохранить файл после сеанса NMAKE; безымянный файл сохраняется на диске с помощью созданного имени файла. Укажите **NOKEEP** или ничего для временного файла. **Сохранить** и **NOKEEP** не учитывается регистр.

## <a name="see-also"></a>См. также

[Подставляемые файлы в Makefile](../build/inline-files-in-a-makefile.md)