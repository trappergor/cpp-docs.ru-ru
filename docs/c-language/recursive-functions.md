---
title: Рекурсивные функции
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
ms.openlocfilehash: 82f0c820ab75fda4bae83db78fa402d7a07cb7fe
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152434"
---
# <a name="recursive-functions"></a>Рекурсивные функции

Любая функция в программе на языке C может вызываться рекурсивно, т. е. может вызывать сама себя. Число рекурсивных вызовов ограничено размером стека. Сведения о параметрах компоновщика, определяющих размер стека, см. в описании параметра компоновщика [/STACK (Stack Allocations)](../build/reference/stack-stack-allocations.md) (/STACK — Распределение стека). При каждом вызове функции для параметров и переменных **auto** и **register** выделяется новая память, чтобы не перезаписывались их значения в предыдущих (незаконченных) вызовах. Параметры доступны непосредственно только экземпляру функции, в котором они были созданы. Последующим экземплярам функции предыдущие параметры непосредственно недоступны.

Обратите внимание, что для переменных, объявленных с описателем **static**, новая память при новом рекурсивном вызове не требуется. Их память существует в течение времени жизни программы. При каждой ссылке на такую переменную осуществляется доступ к той же области памяти.

## <a name="example"></a>Пример

В следующем примере демонстрируются рекурсивные вызовы.

```C
int factorial( int num );      /* Function prototype */

int main()
{
    int result, number;
    .
    .
    .
    result = factorial( number );
}

int factorial( int num )      /* Function definition */
{
    .
    .
    .
    if ( ( num > 0 ) || ( num <= 10 ) )
        return( num * factorial( num - 1 ) );
}
```

## <a name="see-also"></a>См. также

[Вызовы функций](../c-language/function-calls.md)
