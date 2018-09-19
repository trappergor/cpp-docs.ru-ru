---
title: Объявления объединений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unions
- union keyword [C], declarations
- variant records
ms.assetid: 978c6165-e0ae-4196-afa7-6d94e24f62f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b87f3a12de35cb7e7a57c901d65e8df51814fe3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763410"
---
# <a name="union-declarations"></a>Объявления объединений
Объявление объединения определяет набор значений переменных и при необходимости тег, который именует объединение. Значения переменных называются членами объединения и могут иметь различные типы. Объединения аналогичны вариантным записям в других языках.  
  
## <a name="syntax"></a>Синтаксис

*спецификатор-структуры-или-объединения*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-union* *identifier*<sub>opt</sub> **{** *struct-declaration-list* **}**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-or-union* *identifier*  
  
*структура-или-объединение*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**struct**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**union**  
  
*список-объявлений-структуры*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declaration*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declaration-list* *struct-declaration*

Содержимое объединения определено как
  
*объявление-структуры*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*specifier-qualifier-list* *struct-declarator-list*  **;**  
  
*список-спецификаторов-и-квалификаторов*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier* *specifier-qualifier-list*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier* *specifier-qualifier-list*<sub>opt</sub>
  
*список-деклараторов-структуры*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*struct-declarator-list*  **,**  *struct-declarator*
  
Переменная с типом **объединение** хранит одно из значений, определенных в этом типе. Объявления структуры и объединения подчиняются тем же правилам. Объединения также могут иметь битовые поля.  
  
Члены объединений не могут иметь неполный тип, тип `void` или тип функции. Поэтому члены могут быть указателями на объявляемый тип объединения, но не экземпляром объединения.  
  
Объявление типа объединения — это лишь шаблон. Память не резервируется, пока не будет объявлена переменная.  
  
> [!NOTE]
> Если объявляется объединение двух типов и сохраняется одно значение, но для доступа к объединению используется другой тип, результаты будут ненадежными. Например, объявлено объединение **float** и `int`. Сохраняется значение **float**, но программа позднее использует это значение как `int`. Полученное значение будет зависеть от типа внутреннего хранилища для значений **float**. Целочисленное значение будет ненадежным.  
  
## <a name="examples"></a>Примеры

Ниже представлены примеры объединений.  
  
```C
union sign   /* A definition and a declaration */  
{  
    int svar;  
    unsigned uvar;  
} number;  
```  
  
В этом примере определяется переменная объединения с типом `sign` и объявляется переменная `number` с двумя членами: целым числом со знаком `svar` и целым числом без знака `uvar`. В результате этого объявления можно сохранить текущее значение `number` как целое число со знаком или целое число без знака. С данным типом объединения связан тег `sign`.  

```C
union               /* Defines a two-dimensional */  
{                   /*  array named screen */  
    struct      
    {   
      unsigned int icon : 8;    
      unsigned color : 4;  
    } window1;  
    int screenval;  
} screen[25][80];  
```

Массив `screen` содержит 2000 элементов. Каждый элемент массива представляет собой отдельное объединение с двумя членами: `window1` и `screenval`. Член `window1` является структурой с двумя членами-битовыми полями: `icon` и `color`. Член `screenval` представляет собой `int`. В любой момент времени каждый элемент объединения содержит значение `int`, представленное `screenval`, либо структуру, представленную значением `window1`.  
  
**Блок, относящийся только к системам Microsoft**  
  
Вложенные объединения можно объявить анонимно, если они являются членами другой структуры или объединения. Ниже приводится пример безымянного объединения.  
  
```C
struct str  
{  
    int a, b;  
    union            / * Unnamed union */  
    {  
      char c[4];  
      long l;  
      float f;  
   };  
   char c_array[10];  
} my_str;  
.  
.  
.  
my_str.l == 0L;  /* A reference to a field in the my_str union */  
```  
  
Объединения часто являются вложенными в структуре, содержащей поле, которое представляет тип данных, содержащихся в объединении в определенный момент времени. Ниже приводится пример объявления такого объединения.  
  
```C
struct x  
{  
    int type_tag;  
    union  
    {  
      int x;  
      float y;  
    }  
}  
```  
  
Дополнительные сведения о ссылках на объединения см. в разделе [Члены структур и объединений](../c-language/structure-and-union-members.md).  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
[Деклараторы и объявления переменных](../c-language/declarators-and-variable-declarations.md)