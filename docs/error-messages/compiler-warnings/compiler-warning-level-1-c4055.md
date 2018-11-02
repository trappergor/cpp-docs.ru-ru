---
title: Предупреждение компилятора (уровень 1) C4052
ms.date: 11/04/2016
f1_keywords:
- C4055
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: e9fcb4356d993d86b622fd49c4a75d587554f7c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601322"
---
# <a name="compiler-warning-level-1-c4055"></a>Предупреждение компилятора (уровень 1) C4055

> "*преобразования*": из указателя на данные "*тип1*«указатель на функцию»*тип2*"

## <a name="remarks"></a>Примечания

**Устарело:** это предупреждение не создается, Visual Studio 2017 и более поздних версий.

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
