---
title: Предупреждение компилятора (уровень 1) C4055
ms.date: 11/04/2016
f1_keywords:
- C4055
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: 47883f60c3205125a8ee88b804c1d622b3ba0b41
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041033"
---
# <a name="compiler-warning-level-1-c4055"></a>Предупреждение компилятора (уровень 1) C4055

> "*Преобразование*": из указателя данных "*тип1*" в указатель на функцию "*тип2*"

## <a name="remarks"></a>Комментарии

**Устарело:** Это предупреждение не создается в Visual Studio 2017 и более поздних версиях.

Указатель данных приведен (возможно некорректно) к указателю функции. Это предупреждение уровня 1 при использовании параметра /Za и предупреждение уровня 4 при использовании параметра /Ze.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4055:

```C
// C4055.c
// compile with: /Za /W1 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
   return (PFUNC)pi;   // C4055
}
```

При использовании параметра /Ze это предупреждение уровня 4.

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```
