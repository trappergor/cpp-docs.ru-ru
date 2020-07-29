---
title: Предупреждение компилятора (уровень 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: 333f76c2f570832c9d08a7ad666f2540cca37f05
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233344"
---
# <a name="compiler-warning-level-1-c4091"></a>Предупреждение компилятора (уровень 1) C4091

"ключевое слово": игнорируется слева от "Type", если переменная не объявлена

Компилятор обнаружил ситуацию, когда пользователь, вероятно, запланировал объявление переменной, но компилятору не удалось объявить переменную.

## <a name="example"></a>Пример

**`__declspec`** Атрибут в начале объявления определяемого пользователем типа применяется к переменной этого типа. C4091 указывает, что переменная не объявлена. Следующий пример приводит к возникновению ошибки C4091.

```cpp
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

Если идентификатор является typedef, он не может также быть именем переменной. Следующий пример приводит к возникновению ошибки C4091.

```cpp
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```
