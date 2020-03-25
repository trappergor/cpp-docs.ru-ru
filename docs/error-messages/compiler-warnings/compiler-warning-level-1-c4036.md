---
title: Предупреждение компилятора (уровень 1) C4036
ms.date: 11/04/2016
f1_keywords:
- C4036
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
ms.openlocfilehash: 812f36884d24ac988353dbcb18609d4c506e3110
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164265"
---
# <a name="compiler-warning-level-1-c4036"></a>Предупреждение компилятора (уровень 1) C4036

неименованный "тип" в качестве фактического параметра

Не задано имя типа для структуры, объединения, перечисления или класса, используемого в качестве фактического параметра. Если вы создаете прототипы функций с помощью параметра [/Zg](../../build/reference/zg-generate-function-prototypes.md) , компилятор выдает это предупреждение и переводит в комментарий этот формальный параметр в созданном прототипе.

Укажите имя типа, чтобы устранить это предупреждение.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C4036.

```c
// C4036.c
// compile with: /Zg /W1
// D9035 expected
typedef struct { int i; } T;
void f(T* t) {}   // C4036

// OK
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```
