---
title: "&lt;streambuf&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <streambuf>
dev_langs: C++
helpviewer_keywords: streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fa3e46d166ca1807d18caadcca94ec72020a1249
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;
Добавьте стандартный заголовок iostreams \<streambuf>, чтобы определить класс шаблона [basic_streambuf](../standard-library/basic-streambuf-class.md), который является базовым для операций классов iostreams. Этот заголовок обычно включается автоматически при использовании других заголовков потоков ввода-вывода (iostream). Его редко приходится включать напрямую.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <streambuf>  
  
```  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Специализация `basic_streambuf`, использующая `char` в качестве параметров шаблона.|  
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Специализация `basic_streambuf`, использующая `wchar_t` в качестве параметров шаблона.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс basic_streambuf](http://msdn.microsoft.com/en-us/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|Этот класс шаблона описывает абстрактный базовый класс для получения буфера потока, который управляет передачей элементов в определенное представление потока и из него.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)



