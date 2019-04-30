---
title: Ошибка компилятора C3154
ms.date: 11/04/2016
f1_keywords:
- C3154
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
ms.openlocfilehash: 9f7af4e19fab5f5a0539e9fc3bf9dbeffb5c6fbf
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344640"
---
# <a name="compiler-error-c3154"></a>Ошибка компилятора C3154

Ожидается «,» перед многоточием. Не разделенные запятой функциях массивов параметров не поддерживаются многоточия.

Переменный аргумент функции не был объявлен неправильно.

Дополнительные сведения см. в разделе [списками аргументов переменных (...) (C++Выполняет) ](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3154.

```
// C3154.cpp
// compile with: /clr
ref struct R {
   void Func(int ... array<int> ^);   // C3154
   void Func2(int i, ... array<int> ^){}   // OK
   void Func3(array<int> ^){}   // OK
   void Func4(... array<int> ^){}   // OK
};

int main() {
   R ^ r = gcnew R;
   r->Func4(1,2,3);
}
```