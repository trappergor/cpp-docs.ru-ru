---
title: Создание встроенных текстовых | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce0a345c6c2f48d3d5c2e6fb9d9cfc2a5c03e4ed
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720921"
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