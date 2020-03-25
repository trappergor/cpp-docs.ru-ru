---
title: Ошибка средств компоновщика LNK2004
ms.date: 11/04/2016
f1_keywords:
- LNK2004
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
ms.openlocfilehash: 0d26ab12c5b82d52b7dcbb176d9bfa033d7ddfee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194841"
---
# <a name="linker-tools-error-lnk2004"></a>Ошибка средств компоновщика LNK2004

переполнение относительной адресной привязки GP к "Target"; короткий раздел "раздел" слишком велик или выходит за пределы допустимого диапазона.

Раздел слишком большой.

Чтобы устранить эту ошибку, сократите размер короткого раздела, выполнив явное помещение данных в длинные разделы с помощью #pragma раздела (". SectionName", чтения, записи, длинной) и использования `__declspec(allocate(".sectionname"))` в определениях и объявлениях данных.  Например,

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

Можно также переместить логически сгруппированные данные в собственную структуру, которая будет представлять собой коллекцию данных размером более 8 байт, которую компилятор будет выделять в длинном разделе данных.  Например,

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

За этой ошибкой следует `LNK1165`Неустранимая ошибка.
