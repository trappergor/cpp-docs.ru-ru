---
title: Предупреждение компилятора (уровень 4) C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: 1cef70ab02148924bf6a0f29e298b34c54b28bc4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624332"
---
# <a name="compiler-warning-level-4-c4431"></a>Предупреждение компилятора (уровень 4) C4431

отсутствует спецификатор типа — предполагается int. Примечание. C++ не поддерживает тип int по умолчанию

Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: Visual C++ больше не создает нетипизированные идентификаторы как int по умолчанию. Тип идентификатора необходимо указывать явно.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4431.

```
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```