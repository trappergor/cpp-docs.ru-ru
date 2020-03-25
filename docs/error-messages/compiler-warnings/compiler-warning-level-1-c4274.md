---
title: Предупреждение компилятора (уровень 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: 5f2350f275f883e7bf18aa1621d08b34132e8dfb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175850"
---
# <a name="compiler-warning-level-1-c4274"></a>Предупреждение компилятора (уровень 1) C4274

\#Ident игнорируется; #pragma комментарий (exestr, "String") см. в документации.

Директива `#ident`, которая вставляет указанную пользователем строку в объект или исполняемый файл, является устаревшей. Следовательно, компилятор игнорирует директиву.

> [!CAUTION]
>  Предупреждение C4274 рекомендует использовать директиву [комментария #pragma (exestr, "String")](../../preprocessor/comment-c-cpp.md) . Однако этот Совет является устаревшим и будет пересмотрен в будущих выпусках компилятора. Если используется директива `#pragma`, средство компоновщика (LINK. exe) игнорирует запись комментария, созданную директивой, и выдает предупреждение [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Вместо директивы `#ident` рекомендуется использовать в приложении строку ресурса версии файла.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите директиву `#ident "`*string*`"`.

## <a name="see-also"></a>См. также раздел

[comment (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[Предупреждение средств компоновщика LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[Работа с файлами ресурсов](../../windows/working-with-resource-files.md)
