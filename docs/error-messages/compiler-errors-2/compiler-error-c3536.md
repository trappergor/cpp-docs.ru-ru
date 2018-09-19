---
title: Ошибка компилятора C3536 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3536
dev_langs:
- C++
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7585a75ebe9733c228756e92d8e5ae57699aca27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088583"
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