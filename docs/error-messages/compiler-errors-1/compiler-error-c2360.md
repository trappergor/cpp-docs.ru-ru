---
title: Ошибка компилятора C2360 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2360
dev_langs:
- C++
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f443c27c496d5d05c17bde854181b0fdde58f545
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089207"
---
# <a name="compiler-error-c2360"></a>Ошибка компилятора C2360

Пропуск инициализации «идентификатор» метки «case»

Инициализация `identifier` может быть пропущено в `switch` инструкции. Нельзя перейти назад объявление с помощью инициализатора, только если объявление в блоке. (Если она не объявлена в блоке, переменная находится в пределах области до конца `switch` инструкции.)

Следующий пример приводит к возникновению ошибки C2360:

```
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

Возможное решение

```
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```