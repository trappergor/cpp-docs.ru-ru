---
title: Предупреждение о компиляторе (уровень 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: 5d005fccc5920aea61698a65edf9284d56366a1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377079"
---
# <a name="compiler-warning-level-1-c4274"></a>Предупреждение о компиляторе (уровень 1) C4274

\#идентификатор проигнорирован; просмотреть документацию для #pragma комментария (exestr, 'string')

Директива, `#ident` которая вставляет указанную пользователем строку в объект или исполняемый файл, устраняется. Следовательно, компилятор игнорирует директиву.

> [!CAUTION]
> Предупреждение C4274 советует вам использовать [#pragma комментарий (exestr, 'строка')](../../preprocessor/comment-c-cpp.md) директива. Однако этот совет является амортизированным и будет пересмотрен в будущем выпуске компилятора. Если вы `#pragma` используете директиву, инструмент ссылки (LINK.exe) игнорирует запись комментариев, подготовленную директивой, и выдает предупреждение [LNK4229.](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md) Вместо директивы `#ident` мы рекомендуем использовать строку ресурса версии файлов в приложении.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите директиву `#ident "` *строки.* `"`

## <a name="see-also"></a>См. также раздел

[comment (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Linker Инструменты Предупреждение LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Работа с файлами ресурсов](../../windows/working-with-resource-files.md)
