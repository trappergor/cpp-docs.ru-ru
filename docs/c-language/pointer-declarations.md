---
title: Объявления указателей | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pointer declarations
- declarations, pointers
- const keyword [C]
- pointers, declarations
ms.assetid: 8b3b7fc7-f44d-480d-b6f9-cebe4e5462a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f7e5f8933aabe36362938a23c28ed1cd562a579
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205397"
---
# <a name="pointer-declarations"></a>Объявления указателей
Объявление указателя именует переменную указателя и задает тип объекта, на который указывает переменная. Переменная, объявленная как указатель, содержит адрес памяти.  
  
## <a name="syntax"></a>Синтаксис

*declarator*:  
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<sub>opt</sub> *direct-declarator*  

*direct-declarator*:  
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*  
&nbsp;&nbsp;&nbsp;&nbsp;**(** *declarator* **)**  
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator* **[** *constant-expression*<sub>opt</sub> **]**  
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator* **(** *parameter-type-list* **)**  
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator* **(** *identifier-list*<sub>opt</sub> **)**  

*pointer*:  
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *type-qualifier-list*<sub>opt</sub>  
&nbsp;&nbsp;&nbsp;&nbsp;<strong>\*</strong> *type-qualifier-list*<sub>opt</sub> *pointer*  

*type-qualifier-list*:  
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier*  
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier-list* *type-qualifier*  
  
 *type-specifier* предоставляет тип объекта, который может являться любым базовым, структурным типом или типом объединения. Переменные указателя также могут указывать на функции, массивы и другие указателям. (Дополнительные сведения об объявлении и интерпретации более сложных типов указателей см. в разделе [Интерпретация более сложных деклараторов](../c-language/interpreting-more-complex-declarators.md).)  
  
 Создав *описатель типа* **void**, можно отложить спецификацию типа, к которой относится указатель. Этот элемент называется "указатель на **void**" и записывается как `void *`. Переменная, объявленная как указатель на *void*, может использоваться для указания на объект любого типа. Однако для того чтобы выполнять большинство операций с указателем или объектом, на который он указывает, тип, на который он указывает, должен быть явно задан для каждой операции. (Переменные типа **char** <strong>\*</strong> и **void** <strong>\*</strong> могут присваиваться без приведения типа.) Такое преобразование можно выполнить с помощью приведения типа (дополнительные сведения см. в разделе [Преобразования с приведением типа](../c-language/type-cast-conversions.md)).  
  
 *Описатель типа* может иметь значение **const** или **volatile**, либо и то и другое. Они, соответственно, указывают, что указатель не может быть изменен самой программой (**const**) или что указатель может быть изменен каким-либо неподконтрольным программе процессом (**volatile**). (См. раздел [Описатели типа](../c-language/type-qualifiers.md) для получения дополнительной информации о **const** и **volatile**.)  
  
 *Declarator* именует переменную и может включать модификатор типа. Например, если *declarator* представляет массив, тип указателя изменен, чтобы указывать на массив.  
  
 Можно объявить указатель на структуру, объединение или тип перечисления, прежде чем определять тип структуры, объединения или перечисления. Для объявления указателя можно воспользоваться тегом структуры или объединения, как показано в примерах ниже. Такие объявления разрешены, поскольку компилятору не обязательно знать размер структуры или объединения, чтобы выделить пространство для переменной указателя.  
  
## <a name="examples"></a>Примеры  
 В следующих примерах показаны объявления указателей.  
  
```  
char *message; /* Declares a pointer variable named message */  
```  
  
 Указатель *message* указывает на переменную типа **char**.  
  
```  
int *pointers[10];  /* Declares an array of pointers */  
```  
  
 Массив *pointers* содержит 10 элементов; каждый элемент имеет указатель на переменную с типом **int**.  
  
```  
int (*pointer)[10]; /* Declares a pointer to an array of 10 elements */  
```  
  
 Переменная *pointer* указывает на массив с 10 элементами. Каждый элемент в этом массиве имеет тип **int**.  
  
```  
int const *x;      /* Declares a pointer variable, x,  
                      to a constant value */   
```  
  
 Указатель *x* можно изменить, чтобы он указывал на другое значение **int**, но значение, на которое он указывает, изменить невозможно.  
  
```  
const int some_object = 5 ;  
int other_object = 37;  
int *const y = &fixed_object;  
int volatile *const z = &some_object;  
int *const volatile w = &some_object;  
```  
  
 Переменная *y* в следующих объявлениях определяется как постоянный указатель на значение **int**. Значение, на которое он указывает, можно изменить, но указатель должен всегда указывать на одно и то же расположение — адрес *fixed_object*. Аналогично, *z* — это постоянный указатель, но он также объявляется таким образом, чтобы указывать на **int**, значение которого невозможно преобразовать программой. Дополнительный описатель **volatile** указывает, что хотя значение **const int**, на которое указывает *z*, невозможно изменить программой, его допускается изменять процессом, выполняемым одновременно с программой. Объявление *w* указывает, что программа не может изменить значение, на которое указывает указатель, и что программа не может изменить сам указатель.  
  
```  
struct list *next, *previous; /* Uses the tag for list */  
```  
  
 В этом примере объявляются две переменные указателя, *next* и *previous*, указывающие на структурный тип *list*. Это объявление может отображаться перед определением структурного типа *list* (см. следующий пример), если определение типа *list* имеет ту же видимость, что и объявление.  
  
```  
struct list   
{  
    char *token;  
    int count;  
    struct list *next;  
} line;  
```  
  
 Переменная *line* имеет структурный тип с именем *list*. Тип структуры *list* содержит три элемента: указатель на значение **char**, значение **int** и указатель на другую структуру *list*.  
  
```  
struct id   
{  
    unsigned int id_no;  
    struct name *pname;  
} record;  
```  
  
 Переменная *record* имеет структурный тип с именем *id*. Обратите внимание, что *pname* объявляется как указатель на другой тип структуры с именем *name*. Это объявление может отображаться до того, как определен тип *name*.  
  
## <a name="see-also"></a>См. также  
 [Деклараторы и объявления переменных](../c-language/declarators-and-variable-declarations.md)