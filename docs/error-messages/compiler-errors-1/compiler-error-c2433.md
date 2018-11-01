---
title: Ошибка компилятора C2433
ms.date: 11/04/2016
f1_keywords:
- C2433
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
ms.openlocfilehash: 8a98fcf7570605694569b7ae466ae0a3c7cf14bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512062"
---
# <a name="compiler-error-c2433"></a>Ошибка компилятора C2433

«Идентификатор»: «модификатор» не разрешается для объявлений данных

`friend`, `virtual`, И `inline` модификаторы не могут использоваться для объявления данных.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C2433.

```
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```