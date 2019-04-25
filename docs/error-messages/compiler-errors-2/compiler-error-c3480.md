---
title: Ошибка компилятора C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: 2ebcce496fd06c30420558d80cc0a0c9318d4376
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173428"
---
# <a name="compiler-error-c3480"></a>Ошибка компилятора C3480

"переменная": передаваемая переменная в лямбда-выражении должна быть из внешней области видимости функции

Передаваемая переменная в лямбда-выражении не относится к внешней области видимости функции.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите переменную из списка передаваемых параметров в лямбда-выражении.

## <a name="example"></a>Пример

Приведенный ниже пример вызывает ошибку C3480, так как переменная `global` не относится к внешней области видимости функции.

```
// C3480a.cpp

int global = 0;
int main()
{
   [&global] { global = 5; }(); // C3480
}
```

## <a name="example"></a>Пример

В приведенном ниже примере ошибка C3480 устраняется путем удаления переменной `global` из списка передачи лямбда-выражения.

```
// C3480b.cpp

int global = 0;
int main()
{
   [] { global = 5; }();
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)