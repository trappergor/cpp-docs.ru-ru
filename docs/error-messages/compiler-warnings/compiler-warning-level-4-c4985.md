---
title: Предупреждение компилятора (уровень 4) C4985
ms.date: 11/04/2016
f1_keywords:
- C4985
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
ms.openlocfilehash: 87537e960c858cc6741108cf191fbeb2a7a2a8d7
ms.sourcegitcommit: 6e55aeb538b1c39af754f82d6f7738a18f5aa031
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87390017"
---
# <a name="compiler-warning-level-4-c4985"></a>Предупреждение компилятора (уровень 4) C4985

> "*symbol-name*": атрибуты отсутствуют в предыдущем объявлении.

Примечания SAL к текущему объявлению или определению метода отличаются от примечаний к предыдущему объявлению. В определении и объявлениях метода должны использоваться одинаковые примечания SAL.

Язык примечаний к исходному коду (SAL), созданный Майкрософт, предоставляет набор примечаний, описывающих способы использования функцией ее параметров, предположения функции о ее параметрах и гарантии, которые она дает по окончании. Примечания определены в файле заголовка sal.h.

Обратите внимание, что макросы SAL не будут расширяться, если в проекте не [`/analyze`](../../build/reference/analyze-code-analysis.md) указан флаг. При указании **`/analyze`** компилятор может создавать C4985, даже если предупреждения или ошибки не отображались **`/analyze`** .

### <a name="to-correct-this-error"></a>Исправление ошибки

1. В определении метода и всех его объявлениях следует использовать одинаковые примечания SAL.

## <a name="see-also"></a>См. также

[Аннотации SAL](../../c-runtime-library/sal-annotations.md)
