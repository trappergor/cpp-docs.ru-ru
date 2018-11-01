---
title: Предупреждение компилятора (уровень 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: 09ea9e2963735c1e011e25b42b04ad6d67d084a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471725"
---
# <a name="compiler-warning-level-2-c4099"></a>Предупреждение компилятора (уровень 2) C4099

«Идентификатор»: имя типа, ранее отображенное с помощью objecttype1 теперь увидеть при помощи «objecttype2»

Объект, объявленный как структура определяется как класс или объект объявлен как класс, определенный как структура. Компилятор использует тип, заданный в определении.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4099.

```
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```