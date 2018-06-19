---
title: _bstr_t::_bstr_t | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::_bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 824108b78ede3999a83b1c7c1ac75cc847f182f5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413288"
---
# <a name="bstrtbstrt"></a>_bstr_t::_bstr_t
**Блок, относящийся только к системам Microsoft**  
  
 Создает объект `_bstr_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `s1`  
 Копируемый объект `_bstr_t`.  
  
 `s2`  
 Многобайтовая строка.  
  
 `s3`  
 Строка Юникода.  
  
 `var`  
 Объект [_variant_t](../cpp/variant-t-class.md) объекта.  
  
 `bstr`  
 Существующий объект `BSTR`.  
  
 `fCopy`  
 Если имеет значение `false`, то аргумент `bstr` добавляется к новому объекту без создания копии путем вызова функции `SysAllocString`.  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице описываются конструкторы объекта `_bstr_t`.  
  
|Конструктор|Описание|  
|-----------------|-----------------|  
|`_bstr_t( )`|Создает значение по умолчанию `_bstr_t` объекта, который инкапсулирует неопределенный `BSTR` объекта.|  
|`_bstr_t( _bstr_t&`  `s1`  `)`|Создает объект `_bstr_t` как копию другого объекта.<br /><br /> Это *неполную* копия, которая увеличивает счетчик ссылок инкапсулированного `BSTR` объекта вместо создания новой.|  
|`_bstr_t( char*`  `s2`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.<br /><br /> Этот конструктор конструктор сначала преобразует многобайтовую строку в строку Юникода.|  
|`_bstr_t( wchar_t*`  `s3`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.|  
|`_bstr_t( _variant_t&`  `var`  `)`|Создает объект `_bstr_t` из объекта `_variant_t`, предварительно получив объект `BSTR` из инкапсулированного объекта VARIANT.|  
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Создает объект `_bstr_t` из существующего объекта `BSTR` (а не из строки `wchar_t*`). Если `fCopy` имеет значение false, то переданный объект `BSTR` добавляется в новый объект без создания копии при помощи функции `SysAllocString`.<br /><br /> С помощью этого конструктора функции-оболочки в заголовках библиотек типов инкапсулируют и получают право владения объектом `BSTR`, который был возвращен методом интерфейса.|  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t-класс](../cpp/bstr-t-class.md)   
 [Класс _variant_t](../cpp/variant-t-class.md)