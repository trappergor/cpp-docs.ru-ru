---
title: Ошибка средств компоновщика LNK2004
ms.date: 11/04/2016
f1_keywords:
- LNK2004
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
ms.openlocfilehash: 8088494106aa702fda0497fa431e48267167a185
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160423"
---
# <a name="linker-tools-error-lnk2004"></a>Ошибка средств компоновщика LNK2004

Переполнение относительной адресной привязки gp к «целевому объекту»; Сокращенная секция «раздел» слишком велик или вне допустимого диапазона.

Разделе слишком велико.

Чтобы устранить эту ошибку, уменьшите длину сокращенная секция, либо явно помещения данных в длинных секциях с помощью #pragma section (".sectionname", чтение, запись, long) и используя `__declspec(allocate(".sectionname"))` на данных определения и объявления.  Например, примененная к объекту директива

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