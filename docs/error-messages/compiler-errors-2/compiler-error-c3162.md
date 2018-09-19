---
title: Ошибка компилятора C3162 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3162
dev_langs:
- C++
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 529dfa41064e9d22b796b9d079a67b213b816fb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030941"
---
# <a name="compiler-error-c3162"></a>Ошибка компилятора C3162

«Тип»: ссылочный тип, имеющий деструктор не может использоваться как тип статические данные-член «член»

Среда CLR не знает, когда следует запускать определенный пользователем деструктор, если класс также содержит статическую функцию-член.

Деструктор не будут выполняться, если объект удаляется явным образом.

Дополнительные сведения см. в следующих разделах:

- [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)

- [Общие вопросы использования Visual C++ для 64-разрядных систем](../../build/common-visual-cpp-64-bit-migration-issues.md)

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3162.

```
// C3162.cpp
// compile with: /clr /c
ref struct A {
   ~A() { System::Console::WriteLine("in destructor"); }
   static A i;   // C3162
   static A^ a = gcnew A;   // OK
};

int main() {
   A ^ a = gcnew A;
   delete a;
}
```