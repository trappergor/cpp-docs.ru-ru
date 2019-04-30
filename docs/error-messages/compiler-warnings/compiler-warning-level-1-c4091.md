---
title: Компилятор предупреждение (уровень 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: 87432a74dfe7c09a52f436d4e91b3f70eb66856b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410451"
---
# <a name="compiler-warning-level-1-c4091"></a>Компилятор предупреждение (уровень 1) C4091

«ключевое_слово»: игнорируется слева от «тип», когда переменная не объявлена

Компилятор обнаружил ситуацию, когда пользователь, вероятно, предназначен для объявления переменной, когда компилятор не удается объявить переменную.

## <a name="example"></a>Пример

Объект `__declspec` атрибут в начале объявления пользовательского типа относится к переменной этого типа. C4091 указывает, что переменная не объявлена. Следующий пример приводит к возникновению ошибки C4091.

```
// C4091.cpp
// compile with: /W1 /c
__declspec(dllimport) class X {}; // C4091

// __declspec attribute applies to varX
__declspec(dllimport) class X2 {} varX;

// __declspec attribute after the class or struct keyword
// applies to user defined type
class __declspec(dllimport) X3 {};
```

## <a name="example"></a>Пример

Если идентификатор является определением типа, он также не может быть имя переменной. Следующий пример приводит к возникновению ошибки C4091.

```
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```