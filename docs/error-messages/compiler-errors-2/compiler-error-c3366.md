---
title: Ошибка компилятора C3366
ms.date: 11/04/2016
f1_keywords:
- C3366
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
ms.openlocfilehash: 4d1cd510cda9957ced1d9dd5fd8fea267f39220d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507774"
---
# <a name="compiler-error-c3366"></a>Ошибка компилятора C3366

«переменная»: статические элементы данных управляемых или WinRTtypes должны быть определены внутри определения класса

Вы попытались сослаться на статический элемент класса WinRT, .NET или на интерфейс вне определения этого класса или интерфейса.

Компилятору требуется полное определение класса (для передачи метаданных после одного прохода), а статические элементы данных должны инициализироваться внутри класса.

Так, в следующем примере возникает ошибка C3366 и показано, как ее исправить.

```
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```
