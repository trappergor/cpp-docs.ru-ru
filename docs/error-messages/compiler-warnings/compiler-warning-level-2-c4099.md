---
title: Предупреждение компилятора (уровень 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: 97ead14dc9771dc02ad722843ec9fe1a8056e3f6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174288"
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
