---
title: Ошибка средств компоновщика LNK2004 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2004
dev_langs:
- C++
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ade04a6315a8e0193ac882d795ef416d406c1ddb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100777"
---
# <a name="linker-tools-error-lnk2004"></a>Ошибка средств компоновщика LNK2004

Переполнение относительной адресной привязки gp к «целевому объекту»; Сокращенная секция «раздел» слишком велик или вне допустимого диапазона.

Разделе слишком велико.

Чтобы устранить эту ошибку, уменьшите длину сокращенная секция, либо явно помещения данных в длинных секциях с помощью #pragma section (".sectionname", чтение, запись, long) и используя `__declspec(allocate(".sectionname"))` на данных определения и объявления.  Например:

```
#pragma section(".data$mylong", read, write, long)
__declspec(allocate(".data$mylong"))
char    rg0[1] = { 1 };
char    rg1[2] = { 1 };
char    rg2[4] = { 1 };
char    rg3[8] = { 1 };
char    rg4[16] = { 1 };
char    rg5[32] = { 1 };
```

Также можно переместить данные, логически сгруппированы в собственную структуру, которая будет служить коллекцией данных более 8 байт, в которых компилятор будет выделять в разделе данных большой длины.  Например, примененная к объекту директива

```
// from this...
int     w1  = 23;
int     w2 = 46;
int     w3 = 23*3;
int     w4 = 23*4;

// to this...
struct X {
    int     w1;
    int     w2;
    int     w3;
    int     w4;
} x  = { 23, 23*2, 23*3, 23*4 };

```

Эта ошибка сопровождается неустранимой ошибки `LNK1165`.