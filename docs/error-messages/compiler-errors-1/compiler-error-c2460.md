---
title: Ошибка компилятора C2460 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb2d85ffbc7aa799f0688fbb10021a04ef9455ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022625"
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