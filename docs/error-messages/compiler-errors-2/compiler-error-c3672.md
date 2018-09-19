---
title: Ошибка компилятора C3672 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3672
dev_langs:
- C++
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0002b6fdf25374ec0d977c5fa4f450e41d29335f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090650"
---
# <a name="compiler-error-c3672"></a>Ошибка компилятора C3672

выражение псевдо-деструктора можно использовать только как часть вызова функции

Деструктор было вызвано неправильно.  Дополнительные сведения см. в разделе [деструкторы](../../cpp/destructors-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3672.

```
// C3672.cpp
template<typename T>
void f(T* pT) {
   &pT->T::~T;   // C3672
   pT->T::~T();   // OK
};

int main() {
   int i;
   f(&i);
}
```