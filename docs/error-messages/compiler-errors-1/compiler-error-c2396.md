---
title: Ошибка компилятора C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: d320f78937fc60910bbed4a5b1b89841ea674fb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303519"
---
# <a name="compiler-error-c2396"></a>Ошибка компилятора C2396

'your_type::operator'type'' : CLR или WinRT определенное пользователем преобразование functionnot допустимым. Необходимо преобразовать из или преобразовать в: 'T ^', ' е ^ % ", 'T ^ &", где T = ваш «тип»

Функция преобразования в управляемом типе или типе среды выполнения Windows не содержала по крайней мере один параметр, тип которого совпадает с типом, содержащим эту функцию преобразования.

В следующем примере показано возникновение ошибки C2396 и приводятся сведения по ее устранению.

```
// C2396.cpp
// compile with: /clr /c

ref struct Y {
   static operator int(char c);   // C2396

   // OK
   static operator int(Y^ hY);
   // or
   static operator Y^(char c);
};
```