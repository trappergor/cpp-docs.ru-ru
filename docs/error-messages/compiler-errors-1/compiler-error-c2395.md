---
title: Ошибка компилятора C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: dd3bd922e2bfa61da2da87d368bb4b28237161f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303667"
---
# <a name="compiler-error-c2395"></a>Ошибка компилятора C2395

'your_type::operator'op'' : Оператор CLR или WinRT не является допустимым. По крайней мере один параметр должен быть следующих типов: 'T', ' е % ", 'T &", 'T ^ ", 'T ^ %", 'T ^ & ", где T = «your_type»

Оператор в управляемом типе или типе среды выполнения Windows не содержал по крайней мере один параметр, тип которого совпадает с типом значения, возвращаемого оператором.

В следующем примере показано возникновение ошибки C2395 и приводятся сведения по ее устранению.

```
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```