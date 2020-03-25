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
ms.openlocfilehash: 402251592a87b723d75fd1b2cd0786be7b17dbfc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187626"
---
# <a name="_variant_toperator-"></a>_variant_t::operator =

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

## <a name="remarks"></a>Remarks

Оператор присваивает новое значение объекту `_variant_t`.

- **operator = (**  *варсрк*  **)** Назначает существующий `VARIANT` объекту `_variant_t`.

- **operator = (**  *пварсрк*  **)** Назначает существующий `VARIANT` объекту `_variant_t`.

- **operator = (**  *var_t_Src*  **)** Присваивает существующий объект `_variant_t` объекту `_variant_t`.

- **operator = (**  *ССРК*  **)** Присваивает **короткое** целое значение объекту `_variant_t`.

- **operator = (** `lSrc` **)** Присваивает **длинное** целое значение объекту `_variant_t`.

- **operator = (**  *флтсрк*  **)** Присваивает числовое значение **float** объекту `_variant_t`.

- **operator = (**  *дблсрк*  **)** Присваивает значение **типа Double** числовому объекту `_variant_t`.

- **operator = (**  *цисрк*  **)** Назначает объект `CY` объекту `_variant_t`.

- **operator = (**  *бстрсрк*  **)** Назначает объект `BSTR` объекту `_variant_t`.

- **operator = (**  *встрсрк*  **)** Присваивает строку Юникода объекту `_variant_t`.

- **operator = (** `strSrc` **)** Присваивает многобайтовую строку объекту `_variant_t`.

- **operator = (** `bSrc` **)** Присваивает **логическое** значение объекту `_variant_t`.

- **operator = (**  *пдиспсрк*  **)** Назначает объект `VT_DISPATCH` объекту `_variant_t`.

- **operator = (**  *пиункновнсрк*  **)** Назначает объект `VT_UNKNOWN` объекту `_variant_t`.

- **operator = (**  *дексрк*  **)** Присваивает значение `DECIMAL` объекту `_variant_t`.

- **operator = (** `bSrc` **)** Присваивает значение `BYTE` объекту `_variant_t`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _variant_t](../cpp/variant-t-class.md)
