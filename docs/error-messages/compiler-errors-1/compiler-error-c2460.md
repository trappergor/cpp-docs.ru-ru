---
title: Ошибка компилятора C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: 414b6e53cf1610a55db984a1127bfc884102494f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230325"
---
# <a name="compiler-error-c2460"></a>Ошибка компилятора C2460

«идентификатор1»: использует «идентификатор2», определяемый в настоящий момент

Класс или структура (`identifier2`) объявляется как членом самой себя (`identifier1`). Рекурсивные определения классов и структур не допускаются.

Следующий пример приводит к возникновению ошибки C2460:

```
// C2460.cpp
class C {
   C aC;    // C2460
};
```

Вместо этого используйте ссылку на указатель в классе.

```
// C2460.cpp
class C {
   C * aC;    // OK
};
```