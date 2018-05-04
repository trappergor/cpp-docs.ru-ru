---
title: Аргументы функции ссылочного типа | Документы Microsoft
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
ms.openlocfilehash: 83d78aad4285ad711581dbed1c88ef6b9a8a9b24
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="reference-type-function-arguments"></a>Аргументы функции ссылочного типа
Вместо крупных объектов эффективнее бывает передавать функциям ссылки. Это позволяет компилятору передавать адрес объекта, сохраняя при этом синтаксис, который использовался бы для обращения к этому объекту. Рассмотрим следующий пример, в котором используется структура `Date`:  
  
```  
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
  
 Предыдущий код показывает, что члены структуры, передаваемой по ссылке, осуществляется с помощью оператора выбора члена (**.**) вместо оператора выбора члена указателя (**->**).  
  
 Хотя аргументы, передаваемые как ссылочные типы, придерживаются синтаксиса типов, не являющихся указателями, они сохраняют одну важную характеристику типов указателя: они являются изменяемыми, если иное не объявлено как **const**. Поскольку задача приведенного выше кода заключается не в том, чтобы изменить объект `GDate`, более подходящим будет следующий прототип функции:  
  
```  
long JulianFromGregorian( const Date& GDate );  
```  
  
 Этот прототип гарантирует, что функция `JulianFromGregorian` не изменит его аргумент.  
  
 Любая функция прототипом получает ссылочный тип может принимать объект того же типа, вместо него, так как имеется стандартное преобразование из *typename* для * typename ***&**.  
  
## <a name="see-also"></a>См. также  
 [Ссылки](../cpp/references-cpp.md)