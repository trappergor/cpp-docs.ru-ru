---
title: Рекурсивные функции
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
ms.openlocfilehash: 8979d386c6fc3415cd50159250db8488cb917cee
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87199520"
---
# <a name="recursive-functions"></a>Рекурсивные функции

Любая функция в программе на языке C может вызываться рекурсивно, т. е. может вызывать сама себя. Число рекурсивных вызовов ограничено размером стека. Сведения о параметрах компоновщика, определяющих размер стека, см. в описании параметра компоновщика [`/STACK` (распределения стека)](../build/reference/stack-stack-allocations.md). При каждом вызове функции для параметров и переменных **`auto`** и **`register`** выделяется новая память, чтобы не перезаписывались их значения в предыдущих (незаконченных) вызовах. Параметры доступны непосредственно только экземпляру функции, в котором они были созданы. Последующим экземплярам функции предыдущие параметры непосредственно недоступны.

Обратите внимание, что для переменных, объявленных с описателем **`static`** , новая память при новом рекурсивном вызове не требуется. Их память существует в течение времени жизни программы. При каждой ссылке на такую переменную осуществляется доступ к той же области памяти.

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
