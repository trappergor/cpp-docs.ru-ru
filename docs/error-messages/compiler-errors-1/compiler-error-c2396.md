---
title: Ошибка компилятора C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: d320f78937fc60910bbed4a5b1b89841ea674fb7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438103"
---
# <a name="compiler-error-c2396"></a>Ошибка компилятора C2396

":: operator'type '': CLR или WinRT допустимым functionnot определенного пользователем преобразования. Необходимо преобразовать из или в: «T^», «T^%», «T^&», где T = your_type

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