---
title: "Сортировка и поиск | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "данные [CRT], поиск"
  - "поиск [C++]"
  - "поиск [C++], функции поиска CRT"
  - "сортировка данных"
ms.assetid: 15e984f0-e155-46f5-8542-51c458792f54
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Сортировка и поиск
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используйте следующие функции для поиска и сортировки.  
  
### Функции поиска и сортировки  
  
|Функция|Поиск или сортировка|Эквивалент в .NET Framework|  
|-------------|--------------------------|---------------------------------|  
|[bsearch](../c-runtime-library/reference/bsearch.md)|Двоичный поиск|[\<caps:sentence id\="tgt8" sentenceid\="07fe7161f1b3ff07a50d0fdb13bc8ade" class\="tgtSentence"\>System::Collections::ArrayList::BinarySearch\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[bsearch\_s](../c-runtime-library/reference/bsearch-s.md)|Более безопасная версия `bsearch`.|[\<caps:sentence id\="tgt10" sentenceid\="07fe7161f1b3ff07a50d0fdb13bc8ade" class\="tgtSentence"\>System::Collections::ArrayList::BinarySearch\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.binarysearch.aspx)|  
|[\_lfind](../c-runtime-library/reference/lfind.md)|Линейный поиск заданного значения|[\<caps:sentence id\="tgt13" sentenceid\="2b0a5c761626afecd7137a4eab4525f0" class\="tgtSentence"\>System::Collections::ArrayList::Contains\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[\_lfind\_s](../Topic/_lfind_s.md)|Более безопасная версия `_lfind`|[\<caps:sentence id\="tgt15" sentenceid\="2b0a5c761626afecd7137a4eab4525f0" class\="tgtSentence"\>System::Collections::ArrayList::Contains\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.contains.aspx)|  
|[\_lsearch](../c-runtime-library/reference/lsearch.md)|Линейный поиск заданного значения, которое добавляется в массив, если не найдено|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_lsearch\_s](../c-runtime-library/reference/lsearch-s.md)|Более безопасная версия `_lsearch`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[qsort](../c-runtime-library/reference/qsort.md)|Быстрая сортировка|[\<caps:sentence id\="tgt27" sentenceid\="f0305a177c6971f2c3c37537da538229" class\="tgtSentence"\>System::Collections::ArrayList::Sort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
|[qsort\_s](../c-runtime-library/reference/qsort-s.md)|Более безопасная версия `qsort`|[\<caps:sentence id\="tgt29" sentenceid\="f0305a177c6971f2c3c37537da538229" class\="tgtSentence"\>System::Collections::ArrayList::Sort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx)|  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)