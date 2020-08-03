---
title: Возвращаемый тип
ms.date: 11/04/2016
helpviewer_keywords:
- function return types
- return values [C++], function procedures
- function return types, syntax
- return values [C++]
- data types [C++], function return types
- return keyword [C++], function return types
- functions [C++], return types
ms.assetid: 3e5b8a97-b341-48c5-8be8-8986980ef586
ms.openlocfilehash: 1d905e02be02784b562b9d1a8f72a9bfa4057b9b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226331"
---
# <a name="return-type"></a>Возвращаемый тип

Тип возвращаемого значения функции задает размер и тип значения, возвращаемого функцией, и соответствует спецификатору типа в приведенном ниже синтаксисе.

## <a name="syntax"></a>Синтаксис

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* поддерживается только компилятором Майкрософт \*/

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*storage-class-specifier* *declaration-specifiers*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier* *declaration-specifiers*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier* *declaration-specifiers*<sub>opt</sub>

*type-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`void`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`char`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`short`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`int`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int8`**  /\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int16`**  /\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int32`**  /\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`__int64`**  /\* Только для систем Майкрософт \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`long`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`float`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`double`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`signed`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **`unsigned`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-union-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*enum-specifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*typedef-name*

Компонент *type-specifier* может задавать любой базовый тип, тип структуры или тип объединения. Если описатель *type-specifier* не включен, предполагается возвращаемый тип **`int`** .

Тип возвращаемого значения, указанный в определении функции, должен соответствовать возвращаемому типу в объявлениях функций в любом другом месте программы. Функция возвращает значение при выполнении оператора **`return`** , содержащего выражение. Выражение вычисляется, преобразуется в тип возвращаемого значения (при необходимости) и осуществляется возврат в точку, где была вызвана функция. Если функция объявляется с возвращаемым типом **`void`** , оператор return, содержащий выражение, выдает предупреждение и выражение не вычисляется.

В приведенных ниже примерах показываются возвращаемые значения функции.

```C
typedef struct
{
    char name[20];
    int id;
    long class;
} STUDENT;

/* Return type is STUDENT: */

STUDENT sortstu( STUDENT a, STUDENT b )
{
    return ( (a.id < b.id) ? a : b );
}
```

В этом примере определяются тип `STUDENT` с помощью объявления **`typedef`** , а также функция `sortstu`, чтобы иметь возвращаемый тип `STUDENT`. Функция выбирает и возвращает один из двух своих аргументов структуры. В последующих вызовах этой функции компилятор проверяет, что аргументы имеют тип `STUDENT`.

> [!NOTE]
> Эффективность можно увеличить путем передачи указателей на конкретную структуру, а не на всю структуру.

```C
char *smallstr( char s1[], char s2[] )
{
    int i;

    i = 0;
    while ( s1[i] != '\0' && s2[i] != '\0' )
        i++;
    if ( s1[i] == '\0' )
        return ( s1 );
    else
        return ( s2 );
}
```

В этом примере определяется функция, возвращающая указатель на массив символов. Функция принимает в качестве аргументов две строки (два массива) символов и возвращает указатель на более короткую из них. Указатель на массив указывает на первый из элементов массива и имеет его тип; таким образом, возвращаемый тип функции — указатель на тип **`char`** .

Объявлять функции с возвращаемым типом **`int`** перед их вызовом не требуется, хотя рекомендуется использовать прототипы, чтобы для аргументов и возвращаемых значений включалась правильная проверка типа.

## <a name="see-also"></a>См. также

[Определения функций в C](../c-language/c-function-definitions.md)
