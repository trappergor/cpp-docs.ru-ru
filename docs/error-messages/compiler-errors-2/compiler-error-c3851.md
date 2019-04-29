---
title: Ошибка компилятора C3851
ms.date: 09/05/2018
f1_keywords:
- C3851
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
ms.openlocfilehash: 52c4f3a393ffaf2b61a65c8e2e0dcc8efac08288
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380946"
---
# <a name="compiler-error-c3851"></a>Ошибка компилятора C3851

> "*char*": универсальное имя символа не может обозначать символ в базовом наборе символов

## <a name="remarks"></a>Примечания

В коде, скомпилированном как C++, нельзя использовать универсальное имя символа, представляющее символ в основной кодировке исходного кода, вне строки или символьного литерала. Дополнительные сведения см. в разделе [Character Sets](../../cpp/character-sets.md). В коде, скомпилированном как C, нельзя использовать универсальное имя символа для символов в диапазоне от 0x20 до 0x7f, включительно, за исключением 0x24 («$»), 0x40 ("\@"), или 0x60 ("\`").

## <a name="example"></a>Пример

Приведенные ниже примеры кода создают ошибку C3851; также показаны способы ее устранения:

```cpp
// C3851.cpp
int main()
{
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set
   int test2_A = 0;        // OK
}
```