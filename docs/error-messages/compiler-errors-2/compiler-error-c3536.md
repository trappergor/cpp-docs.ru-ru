---
title: Ошибка компилятора C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: a16c5bd46d806d09861d5734b637c2c9d9b2f9d0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345489"
---
# <a name="compiler-error-c3536"></a>Ошибка компилятора C3536

«символ»: нельзя использовать до инициализации

Указанный символ не может использоваться до инициализации. Практически это означает, что переменную нельзя использовать для инициализации самой себя.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Не инициализировать переменную с самим собой.

## <a name="example"></a>Пример

Следующий пример вызывает C3536, поскольку каждая переменная инициализируется с самим собой.

```
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)