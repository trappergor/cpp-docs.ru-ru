---
title: _bstr_t::_bstr_t
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::_bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
ms.openlocfilehash: 3384da733586c828496a8728a0f5855f92eeec35
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190473"
---
# <a name="_bstr_t_bstr_t"></a>_bstr_t::_bstr_t

**Блок, относящийся только к системам Microsoft**

Формирует объект `_bstr_t`.

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

*s1*<br/>
Копируемый объект `_bstr_t`.

*s2*<br/>
Многобайтовая строка.

*S3*<br/>
Строка Юникода.

*var*<br/>
Объект [_variant_t](../cpp/variant-t-class.md) .

*освобождаемой*<br/>
Существующий объект `BSTR`.

*фкопи*<br/>
Если значение равно FALSE, аргумент *BSTR* присоединяется к новому объекту без создания копии путем вызова `SysAllocString`.

## <a name="remarks"></a>Remarks

В следующей таблице описываются конструкторы объекта `_bstr_t`.

|Конструктор|Description|
|-----------------|-----------------|
|`_bstr_t( )`|Конструирует объект `_bstr_t` по умолчанию, который инкапсулирует объект `BSTR` null.|
|`_bstr_t( _bstr_t&`  `s1`  `)`|Создает объект `_bstr_t` как копию другого объекта.<br /><br /> Это *неполная* копия, которая увеличивает счетчик ссылок инкапсулированного `BSTR` объекта вместо создания нового.|
|`_bstr_t( char*`  `s2`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.<br /><br /> Этот конструктор конструктор сначала преобразует многобайтовую строку в строку Юникода.|
|`_bstr_t( wchar_t*`  `s3`  `)`|Создает новый объект `_bstr_t`, вызывая функцию `SysAllocString` для создания нового объекта `BSTR`, а затем инкапсулирует его.|
|`_bstr_t( _variant_t&`  `var`  `)`|Создает объект `_bstr_t` из объекта `_variant_t`, предварительно получив объект `BSTR` из инкапсулированного объекта VARIANT.|
|`_bstr_t( BSTR``bstr` `, bool``fCopy``)`|Создает объект `_bstr_t` из существующего объекта `BSTR` (а не из строки `wchar_t*`). Если *фкопи* имеет значение false, то заданный `BSTR` присоединяется к новому объекту без создания новой копии с `SysAllocString`.<br /><br /> С помощью этого конструктора функции-оболочки в заголовках библиотек типов инкапсулируют и получают право владения объектом `BSTR`, который был возвращен методом интерфейса.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[_bstr_t Class](../cpp/bstr-t-class.md)<br/>
[Класс _variant_t](../cpp/variant-t-class.md)
