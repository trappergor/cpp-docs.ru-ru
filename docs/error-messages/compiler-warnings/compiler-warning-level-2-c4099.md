---
title: Предупреждение компилятора (уровень 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: d685f1f40826b975623dbedc2ba8115c6b3edc45
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052182"
---
# <a name="compiler-warning-level-2-c4099"></a>Предупреждение компилятора (уровень 2) C4099

"идентификатор": имя типа сначала появлялось с помощью "objecttype1", которое теперь было показано с помощью "objecttype2"

Объект, объявленный как структура, определяется как класс, или объект, объявленный как класс, определяется как структура. Компилятор использует тип, заданный в определении.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4099.

```cpp
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```