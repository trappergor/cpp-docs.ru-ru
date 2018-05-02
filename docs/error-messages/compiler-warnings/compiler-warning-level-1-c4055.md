---
title: Ошибка компилятора предупреждение (уровень 1) C4052 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- C4055
dev_langs:
- C++
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29b1c8bcc836e35f7b8b81954ef247527d8ec35e
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="compiler-warning-level-1-c4055"></a>Предупреждение компилятора (уровень 1) C4055

> "*преобразования*": из указателя на данные "*тип1*«указатель на функцию»*тип2*"

## <a name="remarks"></a>Примечания

**Устарело:** это предупреждение не создается в Visual Studio 2017 г. и более поздних версий.

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
