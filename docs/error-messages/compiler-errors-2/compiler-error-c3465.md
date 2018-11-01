---
title: Ошибка компилятора C3465
ms.date: 11/04/2016
f1_keywords:
- C3465
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
ms.openlocfilehash: 8a6cbbc1e75d345d0ebdcfc9e1db32f660c13b01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653418"
---
# <a name="compiler-error-c3465"></a>Ошибка компилятора C3465

для использования типа "тип" необходима ссылка на сборку "сборка"

Перенаправление типов будет работать для клиентского приложения до перекомпиляции клиента. При перекомпиляции потребуется ссылка для каждой сборки, содержащей определение типа, используемого в клиентском приложении.

Дополнительные сведения см. в разделе [Переадресация типа (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Пример

В следующем примере выполняется построение сборки, содержащей новое расположение типа.

```
// C3465.cpp
// compile with: /clr /LD
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>Пример

В следующем примере выполняет построение сборки, которая обычно содержит определение типа, но теперь содержит синтаксис перенаправления для типа.

```
// C3465_b.cpp
// compile with: /clr /LD
#using "C3465.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3465.

```
// C3465_c.cpp
// compile with: /clr
// C3465 expected
#using "C3465_b.dll"
// Uncomment the following line to resolve.
// #using "C3465.dll"

int main() {
   R^ r = gcnew R();
}
```