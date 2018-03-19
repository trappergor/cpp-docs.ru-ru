---
title: "Возвращаемый тип | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function return types
- return values [C++], function procedures
- function return types, syntax
- return values [C++]
- data types [C++], function return types
- return keyword [C++], function return types
- functions [C++], return types
ms.assetid: 3e5b8a97-b341-48c5-8be8-8986980ef586
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9768baa53e39f1b3243aba24385d592010c3d81a
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="return-type"></a>Тип возвращаемого значения
Тип возвращаемого значения функции задает размер и тип значения, возвращаемого функцией, и соответствует спецификатору типа в приведенном ниже синтаксисе.  
  
## <a name="syntax"></a>Синтаксис  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* относится только к системам Microsoft \*/  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *type-specifier*:  
 **void**  
  
 **char**  
  
 **short**  
  
 **int**  
  
 **long**  
  
 **float**  
  
 **double**  
  
 **signed**  
  
 **unsigned**  
  
 *struct-or-union-specifier*  
  
 *enum-specifier*  
  
 *typedef-name*  
  
 Компонент *type-specifier* может задавать любой базовый тип, тип структуры или тип объединения. Если *type-specifier* не включен, предполагается тип возвращаемого значения `int`.  
  
 Тип возвращаемого значения, указанный в определении функции, должен соответствовать возвращаемому типу в объявлениях функций в любом другом месте программы. Функция возвращает значение при выполнении оператора `return`, содержащего выражение. Выражение вычисляется, преобразуется в тип возвращаемого значения (при необходимости) и осуществляется возврат в точку, где была вызвана функция. Если функция объявляется с типом возвращаемого значения `void`, оператор return, содержащий выражение, выдает предупреждение и выражение не вычисляется.  
  
 В приведенных ниже примерах показываются возвращаемые значения функции.  
  
```  
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
  
 В этом примере определяются тип `STUDENT` с помощью объявления `typedef`, а также функция `sortstu`, чтобы иметь возвращаемый тип `STUDENT`. Функция выбирает и возвращает один из двух своих аргументов структуры. В последующих вызовах этой функции компилятор проверяет, что аргументы имеют тип `STUDENT`.  
  
> [!NOTE]
>  Эффективность можно увеличить путем передачи указателей на конкретную структуру, а не на всю структуру.  
  
```  
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
  
 В этом примере определяется функция, возвращающая указатель на массив символов. Функция принимает в качестве аргументов две строки (два массива) символов и возвращает указатель на более короткую из них. Указатель на массив указывает на первый из элементов массива и имеет его тип; таким образом, возвращаемый тип функции — указатель на тип `char`.  
  
 Объявлять функции с возвращаемым типом `int` перед их вызовом не требуется, хотя рекомендуется использовать прототипы, чтобы для аргументов и возвращаемых значений включалась правильная проверка типа.  
  
## <a name="see-also"></a>См. также  
 [Определения функций в C](../c-language/c-function-definitions.md)