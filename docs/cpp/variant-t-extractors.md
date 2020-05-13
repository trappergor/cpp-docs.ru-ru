---
title: Средства извлечения _variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
ms.openlocfilehash: 685df7285e58e0cf2ceeded5ac27641364897298
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187704"
---
# <a name="_variant_t-extractors"></a>Средства извлечения _variant_t

**Блок, относящийся только к системам Microsoft**

Извлечение данных из инкапсулированного `VARIANT` объекта.

## <a name="syntax"></a>Синтаксис

```
operator short( ) const;
operator long( ) const;
operator float( ) const;
operator double( ) const;
operator CY( ) const;
operator _bstr_t( ) const;
operator IDispatch*( ) const;
operator bool( ) const;
operator IUnknown*( ) const;
operator DECIMAL( ) const;
operator BYTE( ) const;
operator VARIANT() const throw();
operator char() const;
operator unsigned short() const;
operator unsigned long() const;
operator int() const;
operator unsigned int() const;
operator __int64() const;
operator unsigned __int64() const;
```

## <a name="remarks"></a>Remarks

Извлекает необработанные данные из инкапсулированного `VARIANT`. Если `VARIANT` еще не является правильным типом, `VariantChangeType` используется для попыток преобразования, а при сбое возникает ошибка:

- **оператор Short ()** Извлекает **короткое** целочисленное значение.

- **оператор Long ()** Извлекает **длинное** целое значение.

- **оператор float ()** Извлекает числовое значение с **плавающей запятой** .

- **оператор Double ()** Извлекает **Двойное** целочисленное значение.

- **оператор CY ()** Извлекает объект `CY`.

- **operator bool ()** Извлекает **логическое** значение.

- **оператор Decimal ()** Извлекает `DECIMAL` значение.

- **Byte оператора ()** Извлекает `BYTE` значение.

- **оператор _bstr_t ()** Извлекает строку, инкапсулированную в объект `_bstr_t`.

- **оператор IDispatch\*()** Извлекает указатель disp-интерфейса из инкапсулированного `VARIANT`. `AddRef` вызывается на результирующем указателе, поэтому для его освобождения необходимо вызвать `Release`.

- **оператор IUnknown\*()** Извлекает указатель COM-интерфейса из инкапсулированного `VARIANT`. `AddRef` вызывается на результирующем указателе, поэтому для его освобождения необходимо вызвать `Release`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _variant_t](../cpp/variant-t-class.md)
