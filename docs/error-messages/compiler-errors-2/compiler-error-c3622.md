---
title: Ошибка компилятора C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: ed307f46db1261d79d5b0ec6b36852cac2e6d13e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781917"
---
# <a name="compiler-error-c3622"></a>Ошибка компилятора C3622

«класс»: класс, объявленный как «ключевое_слово» не может быть создан

Была предпринята попытка создать экземпляр класса, помеченного как [абстрактный](../../extensions/abstract-cpp-component-extensions.md). Класс, помеченный как `abstract` может быть базовым классом, но он не может быть создан.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3622.

```
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
