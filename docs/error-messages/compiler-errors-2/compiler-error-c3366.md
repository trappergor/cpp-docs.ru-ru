---
title: Ошибка компилятора C3366
ms.date: 11/04/2016
f1_keywords:
- C3366
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
ms.openlocfilehash: 5173b1c0df7de6a4e8d9993e680b961a82bb10a7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738470"
---
# <a name="compiler-error-c3366"></a>Ошибка компилятора C3366

"переменная": статические данные членов управляемых или Винрттипес должны быть определены в определении класса

Вы попытались сослаться на статический элемент класса WinRT, .NET или на интерфейс вне определения этого класса или интерфейса.

Компилятору требуется полное определение класса (для передачи метаданных после одного прохода), а статические элементы данных должны инициализироваться внутри класса.

Так, в следующем примере возникает ошибка C3366 и показано, как ее исправить.

```cpp
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```
