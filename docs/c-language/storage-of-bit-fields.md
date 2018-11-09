---
title: Хранение битовых полей
ms.date: 11/04/2016
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
ms.openlocfilehash: 7aa6e02c347ff14bb0552320567b343c7215ebc7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499093"
---
# <a name="storage-of-bit-fields"></a>Хранение битовых полей

**ANSI 3.5.2.1** Порядок назначения битовых полей в целом числе

Битовые поля в целом числе назначаются в направлении от младшего разряда к старшему. В приведенном ниже коде

```
struct mybitfields
{
   unsigned a : 4;
   unsigned b : 5;
   unsigned c : 7;
} test;

int main( void )
{
   test.a = 2;
   test.b = 31;
   test.c = 0;
}
```

биты размещаются следующим образом:

```
00000001 11110010
cccccccb bbbbaaaa
```

Поскольку в процессорах 80x86 младший байт целочисленных значений размещается перед старшим байтом, указанное выше целое число 0x01F2 будет храниться в физической памяти в следующем виде: 0xF2 0x01.

## <a name="see-also"></a>См. также

[Структуры, объединения, перечисления и битовые поля](../c-language/structures-unions-enumerations-and-bit-fields.md)