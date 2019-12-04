---
title: Ошибка компилятора C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: 5020732ce5186ee1c6e9d2ea13f452fe9988bdfa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744840"
---
# <a name="compiler-error-c2396"></a>Ошибка компилятора C2396

"your_type:: оператор'типе" ": допустимое пользовательское преобразование CLR или WinRT функтионнот. Необходимо либо преобразовать из или преобразовать в: 'T ^ ', ' t ^% ', ' t ^ & ', где T = ' your_type '

Функция преобразования в управляемом типе или типе среды выполнения Windows не содержала по крайней мере один параметр, тип которого совпадает с типом, содержащим эту функцию преобразования.

В следующем примере показано возникновение ошибки C2396 и приводятся сведения по ее устранению.

```cpp
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
