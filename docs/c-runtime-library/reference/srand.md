---
title: "srand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "srand"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "srand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "числа, псевдослучайный"
  - "числа, произвольный"
  - "псевдослучайные числа"
  - "случайные числа, создание"
  - "произвольная начальная точка"
  - "произвольная начальная точка, параметр"
  - "srand - функция"
  - "начальные точки"
  - "начальные точки, установка случайного"
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# srand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает стартовое начальное значение для генератора псевдослучайных чисел.  
  
## Синтаксис  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### Параметры  
 `seed`  
 Начальное значение для генерации псевдослучайных чисел  
  
## Заметки  
 Функция `srand` задает отправную точку для генерации ряда псевдослучайных чисел в текущем потоке.  Чтобы повторно инициализировать генератор для создания той же последовательности результатов, следует вызвать функцию `srand` и снова использовать тот же аргумент `seed`.  Любое другое значение для `seed` задает генератору другую стартовую точку в псевдослучайной последовательности.  `rand` извлекает генерируемые псевдослучайные числа.  Вызов `rand` до любого вызова `srand` генерирует ту же последовательность, как и вызов `srand` с `seed` равным 1.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`srand`|\<stdlib.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример для [rand](../Topic/rand.md).  
  
## Эквивалент в .NET Framework  
 [System::Random Class](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [rand](../Topic/rand.md)