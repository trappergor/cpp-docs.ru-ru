---
title: "Аргументы функций ссылочных типов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "аргументы [C++], функция"
  - "аргументы функций, reference-type"
  - "параметры функции, reference-type"
  - "функции [C++], параметры"
  - "передача параметров, аргументы ссылочных типов"
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Аргументы функций ссылочных типов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вместо крупных объектов эффективнее бывает передавать функциям ссылки.  Это позволяет компилятору передавать адрес объекта, сохраняя при этом синтаксис, который использовался бы для обращения к этому объекту.  Рассмотрим следующий пример, в котором используется структура `Date`:  
  
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
  
 В приведенном выше коде указано, что обращение к членам структуры, передаваемой по ссылке, осуществляется при помощи оператора выбора члена \(**.**\), а не оператора выбора указателя на член \(**–\>**\).  
  
 Хотя аргументы, передаваемые как ссылочные типы, придерживаются синтаксиса типов, не являющихся указателями, они сохраняют одну важную характеристику типов указателя: они являются изменяемыми, если не были объявлены как **const**.  Поскольку задача приведенного выше кода заключается не в том, чтобы изменить объект `GDate`, более подходящим будет следующий прототип функции:  
  
```  
long JulianFromGregorian( const Date& GDate );  
```  
  
 Этот прототип гарантирует, что функция `JulianFromGregorian` не изменит его аргумент.  
  
 Любая функция, в прототипе которой указано, что она получает ссылочный тип, может принимать на свое место объект того же типа, поскольку *имя\-типа* стандартно преобразуется в *имя\-типа***&**.  
  
## См. также  
 [Ссылки](../cpp/references-cpp.md)