---
title: "Класс wstring_convert | Microsoft Docs"
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
  - "cvt.wstring_convert"
  - "wstring_convert"
  - "stdext::cvt::wstring_convert"
  - "cvt::wstring_convert"
  - "wstring/stdext::cvt::wstring_convert"
  - "stdext.cvt.wstring_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wstring_convert - класс"
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
caps.latest.revision: 25
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс wstring_convert
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона `wstring_convert` выполняет преобразование между строкой двухбайтовых символов и строкой байтовых символов.  
  
## Синтаксис  
  
```  
template<  
    class Codecvt,  
    class Elem = wchar_t  
>  
class wstring_convert  
```  
  
#### Параметры  
 Codecvt  
 Аспект [языкового стандарта](../standard-library/locale-class.md), представляющий объект преобразования.  
  
 Elem  
 Тип двухбайтового элемента.  
  
## Заметки  
 Класс шаблона описывает объект, управляющий преобразованием между объектами двухбайтовых строк класса `std::basic_string<Elem>` и объектов однобайтовых строк класса `std::basic_string<char>` \(они также называются `std::string`\). Класс шаблона определяет типы `wide_string` и `byte_string` как синонимы для этих двух типов. Преобразование между последовательностями значений `Elem` \(хранятся в объекте `wide_string`\) и многобайтовыми последовательностями \(хранятся в объекте `byte_string`\) выполняется объектом класса `Codecvt<Elem, char, std::mbstate_t>`, который соответствует требованиям аспекта стандартного преобразования кода `std::codecvt<Elem, char, std::mbstate_t>`.  
  
 Объект этого класса шаблона сохраняет:  
  
-   Однобайтовую строку для отображения при ошибках  
  
-   Двухбайтовую строку для отображения при ошибках  
  
-   Указатель на назначенный объект преобразования \(высвобождается при уничтожении объекта wbuffer\_convert\)  
  
-   Объект состояния преобразования типа [state\_type](../Topic/wstring_convert::state_type.md)  
  
-   Счетчик преобразований  
  
### Конструкторы  
  
|||  
|-|-|  
|[wstring\_convert](../Topic/wstring_convert::wstring_convert.md)|Создает объект типа `wstring_convert`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[byte\_string](../Topic/wstring_convert::byte_string.md)|Тип, представляющий однобайтную строку.|  
|[wide\_string](../Topic/wstring_convert::wide_string.md)|Тип, представляющий двухбайтную строку.|  
|[state\_type](../Topic/wstring_convert::state_type.md)|Тип, представляющий состояние преобразования.|  
|[int\_type](../Topic/wstring_convert::int_type.md)|Тип, представляющий целое число.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[from\_bytes](../Topic/wstring_convert::from_bytes.md)|Преобразует строку однобайтовых символов в строку двухбайтовых символов.|  
|[to\_bytes](../Topic/wstring_convert::to_bytes.md)|Преобразует двухбайтовую строку в однобайтовую.|  
|[converted](../Topic/wstring_convert::converted.md)|Возвращает количество успешных преобразований.|  
|[состояние](../Topic/wstring_convert::state.md)|Возвращает объект, представляющий состояние преобразования.|  
  
## Требования  
 **Заголовок:** \<locale\>  
  
 **Пространство имен:** std