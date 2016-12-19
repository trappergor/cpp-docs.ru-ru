---
title: "&lt;fstream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<fstream>"
  - "<fstream>"
  - "std.<fstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fstream - заголовок"
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;fstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет несколько классов, поддерживающих операции iostreams для последовательностей, хранящихся во внешних файлах.  
  
## Синтаксис  
  
```  
  
#include <fstream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[filebuf](../Topic/filebuf.md)|Тип `basic_filebuf`, специализированный на параметрах шаблона `char`.|  
|[fstream](../Topic/fstream.md)|Тип `basic_fstream`, специализированный на параметрах шаблона `char`.|  
|[ifstream](../Topic/ifstream.md)|Тип `basic_ifstream`, специализированный на параметрах шаблона `char`.|  
|[ofstream](../Topic/ofstream.md)|Тип `basic_ofstream`, специализированный на параметрах шаблона `char`.|  
|[wfstream](../Topic/wfstream.md)|Тип `basic_fstream`, специализированный на параметрах шаблона `wchar_t`.|  
|[wifstream](../Topic/wifstream.md)|Тип `basic_ifstream`, специализированный на параметрах шаблона `wchar_t`.|  
|[wofstream](../Topic/wofstream.md)|Тип `basic_ofstream`, специализированный на параметрах шаблона `wchar_t`.|  
|[wfilebuf](../Topic/wfilebuf.md)|Тип `basic_filebuf`, специализированный на параметрах шаблона `wchar_t`.|  
  
### Классы  
  
|||  
|-|-|  
|[basic\_filebuf](../standard-library/basic-filebuf-class.md)|Класс шаблона описывает буфер потока, который управляет передачей элементов типа **Elem**, признаки символов которого определяются с помощью класса **Tr**, в последовательность элементов, сохраненную во внешнем файле, и из нее.|  
|[basic\_fstream](../standard-library/basic-fstream-class.md)|Класс шаблона описывает объект, управляющий извлечением и вставкой элементов и закодированных объектов с помощью буфера потока класса [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\> с элементами типа **Elem**. Их признаки символов определяются классом **Tr**.|  
|[basic\_ifstream](../standard-library/basic-ifstream-class.md)|Класс шаблона описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\> с элементами типа **Elem**. Их признаки символов определяются классом **Tr**.|  
|[basic\_ofstream](../standard-library/basic-ofstream-class.md)|Класс шаблона описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\> с элементами типа **Elem**. Их признаки символов определяются классом **Tr**.|  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)