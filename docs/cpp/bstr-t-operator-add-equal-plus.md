---
title: _bstr_t::operator +=, +
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: 0a2c374fc160a0575e0a17cc85ab51c65fa9392a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390838"
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +

**Блок, относящийся только к системам Microsoft**

Добавляет символы в конец объекта `_bstr_t` или объединяет две строки.

## <a name="syntax"></a>Синтаксис

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>Параметры

*s1*<br/>
Объект `_bstr_t`.

*s2*<br/>
Многобайтовая строка.

*S3*<br/>
Строка Юникода.

## <a name="remarks"></a>Примечания

Эти операторы выполняют объединение строк:

- **оператор += (***s1***)** добавляет символы из инкапсулированного `BSTR` из *s1* в конец этого объекта инкапсулированный `BSTR`.

- **оператор + (***s1***)** возврат нового `_bstr_t` , образуется путем объединения этого объекта `BSTR` с данными о *s1*.

- **оператор + (***s2***&#124;***s1***)** возвращает новый `_bstr_t` , образуется путем объединения Многобайтовая строка *s2*, преобразованной в Юникод, с помощью `BSTR` инкапсулирован в *s1*.

- **оператор + (***s3* **,***s1***)** возвращает новый `_bstr_t` который образуется путем объединения строки Юникод *s3* с `BSTR` инкапсулирован в *s1*.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_bstr_t Class](../cpp/bstr-t-class.md)