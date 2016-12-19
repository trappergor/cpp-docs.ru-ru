---
title: "Класс wbuffer_convert | Microsoft Docs"
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
  - "stdext::cvt::wbuffer_convert"
  - "wbuffer_convert"
  - "stdext.cvt.wbuffer_convert"
  - "cvt.wbuffer_convert"
  - "cvt::wbuffer_convert"
  - "wbuffer/stdext::cvt::wbuffer_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wbuffer_convert - класс"
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс wbuffer_convert
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает буфер потока, который управляет передачей элементов в буфер потока байтов и из него.  
  
## Синтаксис  
  
```  
template<class Codecvt,  
    class Elem = wchar_t,  
    class Traits = std::char_traits<Elem>  
>  
    class wbuffer_convert  
        : public std::basic_streambuf<Elem, Traits>  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Codecvt`|Аспект [языкового стандарта](../standard-library/locale-class.md), представляющий объект преобразования.|  
|`Elem`|Тип двухбайтового элемента.|  
|`Traits`|Признаки, связанные с *Elem*.|  
  
## Заметки  
 Этот класс шаблона описывает буфер потока, который управляет передачей элементов типа `_Elem`, признаки символов которого описываются с помощью класса `Traits`, в буфер потока байтов типа `std::streambuf` и из него.  
  
 Преобразование между последовательностями значений `Elem` и многобайтовыми последовательностями выполняется объектом класса `Codecvt<Elem, char, std::mbstate_t>`, который соответствует требованиям аспекта стандартного преобразования кода `std::codecvt<Elem, char, std::mbstate_t>`.  
  
 Объект этого класса шаблона сохраняет:  
  
-   указатель на базовый буфер потока байтов;  
  
-   указатель на назначенный объект преобразования \(высвобождается при уничтожении объекта [wbuffer\_convert](../standard-library/wbuffer-convert-class.md)\);  
  
-   объект состояния преобразования типа [state\_type](../Topic/wbuffer_convert::state_type.md).  
  
### Конструкторы  
  
|||  
|-|-|  
|[wbuffer\_convert](../Topic/wbuffer_convert::wbuffer_convert.md)|Создает объект типа `wbuffer_convert`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[state\_type](../Topic/wbuffer_convert::state_type.md)|Тип, представляющий состояние преобразования.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[rdbuf](../Topic/wbuffer_convert::rdbuf.md)|Возвращает буфер потока байтов.|  
|[состояние](../Topic/wbuffer_convert::state.md)|Возвращает объект, представляющий состояние преобразования.|  
  
## Требования  
 **Заголовок:** \<locale\>  
  
 **Пространство имен:** std