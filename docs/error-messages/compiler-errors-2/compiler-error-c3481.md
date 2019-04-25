---
title: Ошибка компилятора C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: eff7c7a4f39524aa1d894b7b4590aa809714aae6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173370"
---
# <a name="compiler-error-c3481"></a>Ошибка компилятора C3481

var: переменная, передаваемая в лямбда-выражение, не найдена

Компилятору не удалось найти определение переменной, которая передается в список передаваемых параметров в лямбда-выражении.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите переменную из списка передаваемых параметров в лямбда-выражении.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3481, так как переменная `n` не определена:

```
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)