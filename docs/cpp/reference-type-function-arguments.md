---
title: Аргументы функции ссылочного типа | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- functions [C++], paramters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fad8fc85a37aec80d09ed6df9280a78de0540f01
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409059"
---
# <a name="reference-type-function-arguments"></a>Аргументы функции ссылочного типа
Вместо крупных объектов эффективнее бывает передавать функциям ссылки. Это позволяет компилятору передавать адрес объекта, сохраняя при этом синтаксис, который использовался бы для обращения к этому объекту. Рассмотрим следующий пример, в котором используется структура `Date`:  
  
```cpp 
// reference_type_function_arguments.cpp  
struct Date  
{  
short DayOfWeek;  
short Month;  
short Day;  
short Year;  
};  
  
// Create a Julian date of the form DDDYYYY  
// from a Gregorian date.  
long JulianFromGregorian( Date& GDate )  
{  
static int cDaysInMonth[] = {  
31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31  
   };  
long JDate = 0;  
// Add in days for months already elapsed.  
for ( int i = 0; i < GDate.Month - 1; ++i )  
JDate += cDaysInMonth[i];  
// Add in days for this month.  
JDate += GDate.Day;  
  
// Check for leap year.  
if ( GDate.Year % 100 != 0 && GDate.Year % 4 == 0 )  
JDate++;  
// Add in year.  
JDate *= 10000;  
JDate += GDate.Year;  
  
return JDate;  
}  
  
int main()  
{  
}  
```  
  
 Предыдущий код показывает, что членам структуры, передаваемой по ссылке осуществляется с помощью оператора выбора члена (**.**) вместо указатель оператора выбора члена (**->**).  
  
 Несмотря на то, что аргументы, передаваемые как ссылочные типы Просмотрите синтаксис типов, не являющихся указателями, они сохраняют одну важную характеристику типов указателя: они являются изменяемыми, если иное не объявлено как **const**. Поскольку задача приведенного выше кода заключается не в том, чтобы изменить объект `GDate`, более подходящим будет следующий прототип функции:  
  
```cpp 
long JulianFromGregorian( const Date& GDate );  
```  
  
 Этот прототип гарантирует, что функция `JulianFromGregorian` не изменит его аргумент.  
  
 Любая функция, прототипирован как ссылочный тип может принимать объект одного типа на его месте, так как имеется стандартное преобразование из *typename* для * typename ***&**.  
  
## <a name="see-also"></a>См. также  
 [Ссылки](../cpp/references-cpp.md)