---
title: _variant_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator=
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
ms.openlocfilehash: 6a8f31e8db6f5ca5a680dd47b5d5391c84ce5025
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403325"
---
# <a name="varianttoperator-"></a>_variant_t::operator =

**Блок, относящийся только к системам Microsoft**

## <a name="syntax"></a>Синтаксис

```
_variant_t& operator=(
   const VARIANT& varSrc
);

_variant_t& operator=(
   const VARIANT* pVarSrc
);

_variant_t& operator=(
   const _variant_t& var_t_Src
);

_variant_t& operator=(
   short sSrc
);

_variant_t& operator=(
   long lSrc
);

_variant_t& operator=(
   float fltSrc
);

_variant_t& operator=(
   double dblSrc
);

_variant_t& operator=(
   const CY& cySrc
);

_variant_t& operator=(
   const _bstr_t& bstrSrc
);

_variant_t& operator=(
   const wchar_t* wstrSrc
);

_variant_t& operator=(
   const char* strSrc
);

_variant_t& operator=(
   IDispatch* pDispSrc
);

_variant_t& operator=(
   bool bSrc
);

_variant_t& operator=(
   IUnknown* pSrc
);

_variant_t& operator=(
   const DECIMAL& decSrc
);

_variant_t& operator=(
   BYTE bSrc
);

_variant_t& operator=(
   char cSrc
);

_variant_t& operator=(
   unsigned short usSrc
);

_variant_t& operator=(
   unsigned long ulSrc
);

_variant_t& operator=(
   int iSrc
);

_variant_t& operator=(
   unsigned int uiSrc
);

_variant_t& operator=(
   __int64 i8Src
);

_variant_t& operator=(
   unsigned __int64 ui8Src
);
```

## <a name="remarks"></a>Примечания

Оператор присваивает новое значение объекту `_variant_t`.

- **оператор = (***varSrc***)** присвоение существующего `VARIANT` для `_variant_t` объекта.

- **оператор = (***pVarSrc***)** присвоение существующего `VARIANT` для `_variant_t` объекта.

- **оператор = (***var_t_Src***)** присвоение существующего `_variant_t` объект `_variant_t` объекта.    

- **оператор = (***sSrc***)** назначает **короткие** целочисленное значение, которое `_variant_t` объекта.

- **оператор = (**`lSrc`**)** назначает **long** целочисленное значение, которое `_variant_t` объекта.

- **оператор = (***fltSrc***)** назначает **float** числового значения `_variant_t` объекта.

- **оператор = (***dblSrc***)** назначает **двойные** числового значения `_variant_t` объекта.

- **оператор = (***cySrc***)** назначает `CY` объект `_variant_t` объекта.

- **оператор = (***bstrSrc***)** назначает `BSTR` объект `_variant_t` объекта.

- **оператор = (***wstrSrc***)** присвоение строки Юникода `_variant_t` объекта.

- **оператор = (**`strSrc`**)** присвоение многобайтовой строки `_variant_t` объекта.

- **оператор = (** `bSrc` **)** назначает **bool** значение `_variant_t` объекта.

- **оператор = (***pDispSrc***)** назначает `VT_DISPATCH` объект `_variant_t` объекта.

- **оператор = (***pIUnknownSrc***)** назначает `VT_UNKNOWN` объект `_variant_t` объекта.

- **оператор = (***decSrc***)** назначает `DECIMAL` значение `_variant_t` объекта.

- **оператор = (** `bSrc` **)** назначает `BYTE` значение `_variant_t` объекта.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _variant_t](../cpp/variant-t-class.md)