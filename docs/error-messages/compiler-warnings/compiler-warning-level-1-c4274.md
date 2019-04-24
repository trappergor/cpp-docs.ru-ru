---
title: Компилятор предупреждение (уровень 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: f73fa8e09baab127e7755ebe3def69c2fb585744
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028471"
---
# <a name="compiler-warning-level-1-c4274"></a>Компилятор предупреждение (уровень 1) C4274

\#ident игнорируется; см. документацию для #pragma comment (exestr, "string")

`#ident` Директива, которая вставляет указанной пользователем строки в объекте или исполняемый файл, является устаревшим. Следовательно компилятор игнорирует директиву.

> [!CAUTION]
>  C4274 предупреждение о необходимости использовать [#pragma comment (exestr, "string")](../../preprocessor/comment-c-cpp.md) директива. Тем не менее это является устаревшим и будет изменяться в будущих версиях компилятора. Если вы используете `#pragma` директив, компоновщик (LINK.exe) не обрабатывает эту запись комментария, созданную директивой и выдает предупреждение [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Вместо `#ident` директив, мы рекомендуем использовать строку ресурса версии файла в приложении.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Удалить `#ident "` *строка* `"` директива.

## <a name="see-also"></a>См. также

[comment (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Предупреждение средств компоновщика LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Работа с файлами ресурсов](../../windows/working-with-resource-files.md)