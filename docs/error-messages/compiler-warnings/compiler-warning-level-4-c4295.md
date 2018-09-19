---
title: Предупреждение компилятора (уровень 4) C4295 | Документация Майкрософт
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36c6ac4d8c3e2899b744d1c456ae3079ec031698
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053587"
---
# <a name="compiler-warning-level-4-c4295"></a>Предупреждение компилятора (уровень 4) C4295

> "*массива*": массив слишком мал, чтобы включить завершающий нуль-символ

Массив был инициализирован, но последний символ в массиве не является пустым; доступ к массиву как строку может привести к непредвиденным результатам.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4295. Чтобы устранить эту проблему, можно объявить размер массива больше, для хранения завершающий нуль-символ из строки инициализатор, или могут применить список инициализатора массива намерений clear, что это массив `char`, не строку нуль-символом null.

```C
// C4295.c
// compile with: /W4


int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
