---
title: _variant_t::_variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::_variant_t
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
ms.openlocfilehash: fff116ef04967a1887eaa075d92d3ea0283d5427
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187535"
---
# <a name="_variant_t_variant_t"></a>_variant_t::_variant_t

**Блок, относящийся только к системам Microsoft**

Формирует объект `_variant_t`.

## <a name="syntax"></a>Синтаксис

```
_variant_t( ) throw( );

_variant_t(
   const VARIANT& varSrc
);

_variant_t(
   const VARIANT* pVarSrc
);

_variant_t(
   const _variant_t& var_t_Src
);

_variant_t(
   VARIANT& varSrc,
   bool fCopy
);

_variant_t(
   short sSrc,
   VARTYPE vtSrc = VT_I2
);

_variant_t(
   long lSrc,
   VARTYPE vtSrc = VT_I4
);

_variant_t(
   float fltSrc
) throw( );

_variant_t(
   double dblSrc,
   VARTYPE vtSrc = VT_R8
);

_variant_t(
   const CY& cySrc
) throw( );

_variant_t(
   const _bstr_t& bstrSrc
);

_variant_t(
   const wchar_t *wstrSrc
);

_variant_t(
   const char* strSrc
);

_variant_t(
   IDispatch* pDispSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   bool bSrc
) throw( );

_variant_t(
   IUnknown* pIUknownSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   const DECIMAL& decSrc
) throw( );

_variant_t(
   BYTE bSrc
) throw( );

variant_t(
   char cSrc
) throw();

_variant_t(
   unsigned short usSrc
) throw();

_variant_t(
   unsigned long ulSrc
) throw();

_variant_t(
   int iSrc
) throw();

_variant_t(
   unsigned int uiSrc
) throw();

_variant_t(
   __int64 i8Src
) throw();

_variant_t(
   unsigned __int64 ui8Src
) throw();
```

#### <a name="parameters"></a>Параметры

*варсрк*<br/>
Объект `VARIANT`, который необходимо скопировать в новый объект `_variant_t`.

*пварсрк*<br/>
Указатель на объект `VARIANT`, который необходимо скопировать в новый объект `_variant_t`.

*var_t_Src*<br/>
Объект `_variant_t`, который необходимо скопировать в новый объект `_variant_t`.

*фкопи*<br/>
Если **значение равно false**, предоставленный объект `VARIANT` присоединяется к новому объекту `_variant_t` без создания новой копии с помощью `VariantCopy`.

*ИСРК, ССРК*<br/>
Целочисленное значение, которое необходимо скопировать в новый объект `_variant_t`.

*втсрк*<br/>
`VARTYPE` для нового объекта `_variant_t`.

*Флтсрк, Дблсрк*<br/>
Числовое значение, которое необходимо скопировать в новый объект `_variant_t`.

*цисрк*<br/>
Объект `CY`, который необходимо скопировать в новый объект `_variant_t`.

*бстрсрк*<br/>
Объект `_bstr_t`, который необходимо скопировать в новый объект `_variant_t`.

*Стрсрк, Встрсрк*<br/>
Строка, которую необходимо скопировать в новый объект `_variant_t`.

*бсрк*<br/>
**Логическое** значение, которое должно быть скопировано в новый объект `_variant_t`.

*пиукновнсрк*<br/>
Указатель COM-интерфейса на объект VT_UNKNOWN, который должен быть инкапсулирован в новый объект `_variant_t`.

*пдиспсрк*<br/>
Указатель COM-интерфейса на объект VT_DISPATCH, который должен быть инкапсулирован в новый объект `_variant_t`.

*дексрк*<br/>
Значение `DECIMAL`, которое необходимо скопировать в новый объект `_variant_t`.

*бсрк*<br/>
Значение `BYTE`, которое необходимо скопировать в новый объект `_variant_t`.

*ксрк*<br/>
Значение **типа char** , которое копируется в новый объект `_variant_t`.

*уссрк*<br/>
**Короткое значение без знака** , которое должно быть скопировано в новый объект `_variant_t`.

*улсрк*<br/>
Значение **типа Long без знака** , которое должно быть скопировано в новый объект `_variant_t`.

*исрк*<br/>
Значение **типа int** , которое должно быть скопировано в новый объект `_variant_t`.

*уисрк*<br/>
Значение **целого числа без знака** , которое необходимо скопировать в новый объект `_variant_t`.

*i8Src*<br/>
Значение **__int64** , которое должно быть скопировано в новый объект `_variant_t`.

*ui8Src*<br/>
Значение **__int64 без знака** , которое копируется в новый объект `_variant_t`.

## <a name="remarks"></a>Remarks

- **_variant_t ()** Конструирует пустой объект `_variant_t` `VT_EMPTY`.

- **_variant_t (variant &**  *варсрк*  **)** Конструирует объект `_variant_t` из копии объекта `VARIANT`. Тип variant сохранен.

- **_variant_t (variant** <strong>\*</strong> *пварсрк* **)** Конструирует объект `_variant_t` из копии объекта `VARIANT`. Тип variant сохранен.

- **_variant_t (_variant_t &**  *var_t_Src*  **)** Конструирует объект `_variant_t` из другого `_variant_t` объекта. Тип variant сохранен.

- **_variant_t (variant &** *варсрк* **, bool**`fCopy` **)** Конструирует объект `_variant_t` из существующего объекта `VARIANT`. Если *фкопи* имеет **значение false**, объект **Variant** присоединяется к новому объекту без создания копии.

- **_variant_t (Short***ссрк* **, VarType**`vtSrc` **= VT_I2)** Конструирует объект `_variant_t` типа VT_I2 или VT_BOOL из **короткого** целочисленного значения. Любая другая `VARTYPE` приводит к ошибке E_INVALIDARG.

- **_variant_t (long**`lSrc` **, VARTYPE**`vtSrc` **= VT_I4)** Конструирует объект `_variant_t` типа VT_I4, VT_BOOL или VT_ERROR из **длинного** целочисленного значения. Любая другая `VARTYPE` приводит к ошибке E_INVALIDARG.

- **_variant_t (float**`fltSrc` **)** Конструирует объект `_variant_t` типа VT_R4 из числового значения **float** .

- **_variant_t (double**`dblSrc` **, VARTYPE**`vtSrc` **= VT_R8)** Конструирует объект `_variant_t` типа VT_R8 или VT_DATE из **двойного** числового значения. Любая другая `VARTYPE` приводит к ошибке E_INVALIDARG.

- **_variant_t (CY &** `cySrc` **)** Конструирует объект `_variant_t` типа VT_CY из объекта `CY`.

- **_variant_t (_bstr_t &** `bstrSrc` **)** Конструирует объект `_variant_t` типа VT_BSTR из объекта `_bstr_t`. Выделяется новый параметр `BSTR`.

- **_variant_t (wchar_t** <strong>\*</strong> *встрсрк*  **)** Конструирует объект `_variant_t` типа VT_BSTR из строки Юникода. Выделяется новый параметр `BSTR`.

- **_variant_t (char** <strong>\*</strong>`strSrc` **)** Конструирует объект `_variant_t` типа VT_BSTR из строки. Выделяется новый параметр `BSTR`.

- **_variant_t (bool**`bSrc` **)** Конструирует объект `_variant_t` типа VT_BOOL из **логического** значения.

- **_variant_t (IUnknown** <strong>\*</strong>`pIUknownSrc` **, bool**`fAddRef` **= true)** Конструирует объект `_variant_t` типа VT_UNKNOWN из указателя COM-интерфейса. Если `fAddRef` имеет **значение true**, то `AddRef` вызывается в указанном указателе интерфейса, чтобы соответствовать вызову `Release`, который будет происходить при уничтожении объекта `_variant_t`. Вам нужно вызвать `Release` в указанном указателе интерфейса. Если `fAddRef` имеет **значение false**, этот конструктор принимает владение переданным указателем интерфейса; не вызывайте `Release` для заданного указателя интерфейса.

- **_variant_t (IDispatch** <strong>\*</strong>`pDispSrc` **, bool**`fAddRef` **= true)** Конструирует объект `_variant_t` типа VT_DISPATCH из указателя COM-интерфейса. Если `fAddRef` имеет **значение true**, то `AddRef` вызывается в указанном указателе интерфейса, чтобы соответствовать вызову `Release`, который будет происходить при уничтожении объекта `_variant_t`. Вам нужно вызвать `Release` в указанном указателе интерфейса. Если `fAddRef` имеет **значение false**, этот конструктор принимает владение переданным указателем интерфейса; не вызывайте `Release` для заданного указателя интерфейса.

- **_variant_t (десятичное &** `decSrc` **)** Конструирует объект `_variant_t` типа VT_DECIMAL из значения `DECIMAL`.

- **_variant_t (байт**`bSrc` **)** Конструирует объект `_variant_t` типа `VT_UI1` из значения `BYTE`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Класс _variant_t](../cpp/variant-t-class.md)
