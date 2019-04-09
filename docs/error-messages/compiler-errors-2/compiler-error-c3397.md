---
title: Ошибка компилятора C3397
ms.date: 11/04/2016
f1_keywords:
- C3397
helpviewer_keywords:
- C3397
ms.assetid: a8536e87-79c4-4ed7-bd96-42704d06391f
ms.openlocfilehash: c6ca48eb53cf1c6d661a201fa8c4d2539669b9bf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58772856"
---
# <a name="compiler-error-c3397"></a>Ошибка компилятора C3397

Агрегатная инициализация не допускается в аргументах по умолчанию

Массив был объявлен неправильно.  См. в разделе [массивы](../../extensions/arrays-cpp-component-extensions.md) Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3397:

```
// C3397.cpp
// compile with: /clr
// /clr /c
void Func(array<int> ^p = gcnew array<int> { 1, 2, 3 });   // C3397
void Func2(array<int> ^p = gcnew array<int> (3));   // OK

int main() {
   array<int> ^p = gcnew array<int> { 1, 2, 3};   // OK
}
```