---
title: "Деклараторы и объявления переменных | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- declaring variables, declarators
- declarators, definition
- declaring variables, declaration statements
ms.assetid: 5fd67a6a-3a6a-4ec9-b257-3f7390a48d40
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 08165d5e6308697ec75a6d03751b26fb626dbb15
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="declarators-and-variable-declarations"></a>Деклараторы и объявления переменных
В остальной части данного раздела описывается форма и значение объявлений для переменных типов, включенных в этот список. В частности, в остальных разделах объясняется, как объявить следующие объекты.  
  
|Тип переменной|Описание|  
|----------------------|-----------------|  
|[Простые переменные](../c-language/simple-variable-declarations.md)|Однозначные переменные целочисленного типа или типа с плавающей запятой|  
|[Массивы](../c-language/array-declarations.md)|Переменные, состоящие из коллекции элементов того же типа|  
|[Указатели](../c-language/pointer-declarations.md)|Переменные, указывающие на другие переменные и содержащие расположения переменных (в виде адресов) вместо значений|  
|[Переменные перечисления](../c-language/c-enumeration-declarations.md)|Простые переменные с целочисленным типом, содержащие одно значение из набора именованных целочисленных констант|  
|[Структуры](../c-language/structure-declarations.md)|Переменные, состоящие из коллекции значений, которые могут иметь разные типы|  
|[Объединения](../c-language/union-declarations.md)|Переменные, состоящие из нескольких значений разных типов, занимающих одинаковое пространство для хранения|  
  
 Декларатор — это часть объявления, задающая имя, которое нужно вставить в программу. Он может включать модификаторы, например **\*** (указатель на), и любые ключевые слова соглашения о вызовах Майкрософт.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 В деклараторе  
  
```  
__declspec(thread) char *var;  
```  
  
 `char` — это описатель типа, `__declspec(thread)` и `*` — это модификаторы, а `var` — это имя идентификатора.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
 Деклараторы используются для объявления массивов значений, указателей на значения и функций, возвращающих значения заданного типа. Деклараторы отображаются в объявлениях массивов и указателей, описанных далее в этом разделе.  
  
## <a name="syntax"></a>Синтаксис  
 *declarator*:  
 &nbsp;&nbsp;*pointer*<sub>opt</sub> *direct-declarator*  
  
 *direct-declarator*:  
 &nbsp;&nbsp;*identifier*  
 &nbsp;&nbsp;**(**  *declarator*  **)**  
 &nbsp;&nbsp;*direct-declarator*  **[**  *constant-expression*<sub>opt</sub> **]**  
 &nbsp;&nbsp;*direct-declarator*  **(**  *parameter-type-list*  **)**  
 &nbsp;&nbsp;*direct-declarator*  **(**  *identifier-list*<sub>opt</sub> **)**  
  
 *pointer*:  
 &nbsp;&nbsp;**\*** *type-qualifier-list*<sub>opt</sub>  
 &nbsp;&nbsp;**\*** *type-qualifier-list*<sub>opt</sub> *pointer*  
  
 *type-qualifier-list*:  
 &nbsp;&nbsp;*type-qualifier*  
 &nbsp;&nbsp;*type-qualifier-list type-qualifier*  
  
> [!NOTE]
>  См. соответствующий синтаксис для *объявления* в разделе [Обзор объявлений](../c-language/overview-of-declarations.md) или [Краткие сведения о синтаксисе языка C](../c-language/c-language-syntax-summary.md) для получения сведений о синтаксисе, который ссылается на *декларатор*.  
  
 Если декларатор состоит из неизмененного идентификатора, объявляемый элемент имеет базовый тип. Если звездочка (**\***) отображается слева от идентификатора, тип изменяется на тип указателя. Если после идентификатора следуют квадратные скобки (**[ ]**), тип изменяется на тип массива. Если после идентификатора следуют скобки, тип меняется на тип функции. Дополнительные сведения об интерпретации приоритетности в пределах объявлений см. в разделе [Интерпретация более сложных деклараторов](../c-language/interpreting-more-complex-declarators.md).  
  
 Каждый декларатор объявляет по крайней мере один идентификатор. Декларатор должен включать описатель типа, чтобы называться полным объявлением. Описатель типа предоставляет тип элементов типа массива, тип объекта, к которому относится тип указателя, или тип возвращаемого значения функции.  
  
 Объявления [массивов](../c-language/array-declarations.md) и [указателей](../c-language/pointer-declarations.md) более подробно обсуждаются далее в этом разделе. В следующем примере проиллюстрировано несколько простых форм деклараторов.  
  
```  
int list[20]; // Declares an array of 20 int values named list  
char *cp;     // Declares a pointer to a char value  
double func( void ); // Declares a function named func, with no   
                     // arguments, that returns a double value  
int *aptr[10] // Declares an array of 10 pointers  
```  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Компилятор Microsoft C не ограничивает число деклараторов, которые могут изменять арифметические, структурные типы или типы объединений. Это число ограничивается только объемом доступной памяти.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Объявления и типы](../c-language/declarations-and-types.md)