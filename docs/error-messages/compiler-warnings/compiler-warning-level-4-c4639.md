---
title: Предупреждение компилятора (уровень 4) C4639
ms.date: 11/04/2016
f1_keywords:
- C4639
helpviewer_keywords:
- C4639
ms.assetid: f94f7392-cdbb-4bf4-8a00-20dc90d3efe9
ms.openlocfilehash: d379b159cd7fd67629ea74c47a9e55f1167dc74a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198254"
---
# <a name="compiler-warning-level-4-c4639"></a>Предупреждение компилятора (уровень 4) C4639

Ошибка MSXML, комментарии XML-документа не будут обработаны. reason

Это предупреждение может возникнуть по ряду причин.

Чтобы устранить это предупреждение, сделайте следующее:

- RECOMPILE.

- Переустановите MSXML, переустановив среду CLR.

- Измените или удалите комментарий к документации, вызывающий предупреждение и перекомпиляцию.

При выдаче C4639 все дальнейшие обработки комментариев XML отключаются, и XDC-файл не создается.
