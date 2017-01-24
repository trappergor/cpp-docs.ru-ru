---
title: "_bstr_t::_bstr_t | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::_bstr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bstr_t - класс"
  - "_bstr_t - метод"
  - "BSTR - объект"
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::_bstr_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Создает объект `_bstr_t`.  
  
## Синтаксис  
  
```  
_bstr_t( ) throw( );   
_bstr_t(  
   const _bstr_t& s1   
) throw( );  
_bstr_t(  
   const char* s2   
);  
_bstr_t(  
   const wchar_t* s3   
);  
_bstr_t(  
   const _variant_t& var   
);  
_bstr_t(  
   BSTR bstr,  
   bool fCopy   
);  
```  
  
#### Параметры  
 `s1`  
 Копируемый объект `_bstr_t`.  
  
 `s2`  
 Многобайтовая строка.  
  
 `s3`  
 Строка Юникода.  
  
 `var`  
 Объект [\_variant\_t](../cpp/variant-t-class.md).  
  
 `bstr`  
 Существующий объект `BSTR`.  
  
 `fCopy`  
 Если имеет значение `false`, то аргумент `bstr` добавляется к новому объекту без создания копии путем вызова функции `SysAllocString`.  
  
## Заметки  
 В следующей таблице описываются конструкторы объекта `_bstr_t`.  
  
|Конструктор|Описание|  
|-----------------|--------------|  
|`_bstr_t( )`|Создает объект `_bstr_t` по умолчанию, который инкапсулирует неопределенный объект `BSTR`.|  
|`_bstr_t( _bstr_t&`  `s1`  `)`|Создает объект `_bstr_t` как копию другого объекта.<br /><br /> Это *неполная* копия, которая увеличивает счетчик ссылок инкапсулированного объекта `BSTR`, а не создает новый.|  
|`_bstr_t( char*`  `s2`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.<br /><br /> Этот конструктор конструктор сначала преобразует многобайтовую строку в строку Юникода.|  
|`_bstr_t( wchar_t*`  `s3`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.|  
|`_bstr_t( _variant_t&`  `var`  `)`|Создает объект `_bstr_t` из объекта `_variant_t`, предварительно получив объект `BSTR` из инкапсулированного объекта VARIANT.|  
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Создает объект `_bstr_t` из существующего объекта `BSTR` \(а не из строки `wchar_t*`\).  Если `fCopy` имеет значение false, то переданный объект `BSTR` добавляется в новый объект без создания копии при помощи функции `SysAllocString`.<br /><br /> С помощью этого конструктора функции\-оболочки в заголовках библиотек типов инкапсулируют и получают право владения объектом `BSTR`, который был возвращен методом интерфейса.|  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Класс \_bstr\_t](../cpp/bstr-t-class.md)   
 [Класс \_variant\_t](../cpp/variant-t-class.md)