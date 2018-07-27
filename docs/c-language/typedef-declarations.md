---
title: Объявления Typedef | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declarations, typedef
- typedef declarations
- types [C], declarations
ms.assetid: e92a3b82-9269-4bc6-834a-6f431ccac83e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 192f7ab037362219261852cfdb0a5eac53e5df9f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391656"
---
# <a name="typedef-declarations"></a>Объявления Typedef
Объявление typedef — это объявление с typedef в качестве класса хранения. Декларатор становится новым типом. Объявления typedef можно использовать для создания более коротких или более понятных имен для типов, уже определенных в языке C или объявленных пользователем. Имена typedef позволяют инкапсулировать детали реализации, которые могут измениться.  
  
 Объявление typedef интерпретируется точно так же, как и объявление переменной или функции, но идентификатор становится синонимом типа, а не принимает тип, указанный в объявлении.  
  
## <a name="syntax"></a>Синтаксис  
 `declaration`:  
 *declaration-specifiers init-declarator-list* opt **;**  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *storage-class-specifier*:  
 `typedef`  
  
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
  
 *typedef-name*:  
 *identifier*  
  
 Обратите внимание, что объявление typedef не создает типы. Оно создает синонимы для существующих типов или имена для типов, которые могут определяться другими способами. Если имя typedef используется как спецификатор типа, его можно использовать в сочетании с определенными спецификаторами типа (но нельзя использовать с другими спецификаторами). К допустимым модификаторам относятся **const** и `volatile`.  
  
 Имена Typedef используют то же пространство имен, что и обычные идентификаторы (дополнительные сведения см. в статье [Пространства имен](../c-language/name-spaces.md)). Поэтому в программе может присутствовать имя typedef и идентификатор с тем же именем в локальной области. Пример:  
  
```  
typedef char FlagType;  
  
int main()  
{  
}  
  
int myproc( int )  
{  
    int FlagType;  
}  
```  
  
 При объявлении в локальной области идентификатора с тем же именем, что и имя typedef, или при объявлении члена структуры либо объединения в той же области или во внутренней области обязательно должен указываться спецификатор типа. Следующий пример иллюстрирует это ограничение:  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 Чтобы повторно использовать имя `FlagType` для идентификатора, члена структуры или члена объединения, необходимо указать тип:  
  
```  
const int FlagType;  /* Type specifier required */  
```  
  
 Недостаточно написать  
  
```  
const FlagType;      /* Incomplete specification */  
```  
  
 поскольку `FlagType` воспринимается как часть типа, а не как заново объявляемый идентификатор. Это объявление недопустимо, как и  
  
```  
int;  /* Illegal declaration */  
```  
  
 С помощью typedef можно объявить любой тип, включая типы указателей, функций и массивов. Имя typedef для типа указателя на структуру или объединение можно объявить до определения типа структуры или объединения, если только определение находится в той же области видимости, что и объявление.  
  
 Имена typedef можно использовать, чтобы сделать код более понятным. Все три следующих объявления `signal` задают один и тот же тип, причем в первом объявлении имена typedef не используются.  
  
```  
typedef void fv( int ), (*pfv)( int );  /* typedef declarations */  
  
void ( *signal( int, void (*) (int)) ) ( int );  
fv *signal( int, fv * );   /* Uses typedef type */  
pfv signal( int, pfv );    /* Uses typedef type */  
```  
  
## <a name="examples"></a>Примеры  
 В следующих примерах показаны объявления typedef:  
  
```  
typedef int WHOLE; /* Declares WHOLE to be a synonym for int */  
```  
  
 Обратите внимание, что теперь имя `WHOLE` может использоваться в объявлении переменных, например `WHOLE i;` или `const WHOLE i;`. Однако объявление `long WHOLE i;` недопустимо.  
  
```  
typedef struct club   
{  
    char name[30];  
    int size, year;  
} GROUP;  
```  
  
 Этот оператор объявляет имя `GROUP` как тип структуры с тремя членами. Поскольку также указан тег структуры, `club`, в объявлениях можно использовать как имя typedef (`GROUP`), так и тег структуры. С тегом необходимо использовать ключевое слово struct; с именем typedef использование ключевого слова struct не допускается.  
  
```  
typedef GROUP *PG; /* Uses the previous typedef name   
                      to declare a pointer            */  
```  
  
 Тип `PG` объявлен как указатель на тип `GROUP`, который, в свою очередь, определен как тип структуры.  
  
```  
typedef void DRAWF( int, int );  
```  
  
 В этом примере задан тип `DRAWF` для функции, не возвращающей никакого значения и принимающей два аргумента int. Это означает, например, что объявление  
  
```  
DRAWF box;   
```  
  
 эквивалентно объявлению  
  
```  
void box( int, int );  
```  
  
## <a name="see-also"></a>См. также  


