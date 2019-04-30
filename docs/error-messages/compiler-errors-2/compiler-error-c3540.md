---
title: Ошибка компилятора C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 57e4145557272f76a890a356c79982346cd74d7e
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345472"
---
# <a name="compiler-error-c3540"></a>Ошибка компилятора C3540

«Тип»: невозможно применить sizeof к типу, который содержит «auto»

[Sizeof](../../cpp/sizeof-operator.md) оператор не может применяться к указанному типу, так как она содержит `auto` спецификатор.

## <a name="example"></a>Пример

Следующий пример вызывает ошибку C3540.

```
// C3540.cpp
// Compile with /Zc:auto
int main() {
    auto x = 123;
    sizeof(x);    // OK
    sizeof(auto); // C3540
    return 0;
}
```

## <a name="see-also"></a>См. также

[Ключевое слово auto](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (выведение типа переменной)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[Оператор sizeof](../../cpp/sizeof-operator.md)