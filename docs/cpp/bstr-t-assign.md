---
title: _bstr_t::Assign
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Assign
helpviewer_keywords:
- Assign method [C++]
ms.assetid: 2e209bbe-77ca-4598-86d5-6c2ea213f43c
ms.openlocfilehash: e11c7e6abd2d5832c57d0379473c6783128f63e3
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87521152"
---
# <a name="_bstr_tassign"></a>_bstr_t::Assign

**Блок, относящийся только к системам Microsoft**

Копирует строку `BSTR` в строку `BSTR`, инкапсулированную объектом `_bstr_t`.

## <a name="syntax"></a>Синтаксис

```cpp
void Assign(
   BSTR s
);
```

#### <a name="parameters"></a>Параметры

*#d0*<br/>
Объект `BSTR`, копируемый в объект `BSTR`, инкапсулированный объектом `_bstr_t`.

## <a name="remarks"></a>Примечания

**Assign** выполняет двоичную копию, что означает копирование всей длины, `BSTR` независимо от содержимого.

## <a name="example"></a>Пример

```cpp
// _bstr_t_Assign.cpp

#include <comdef.h>
#include <stdio.h>

int main()
{
    // creates a _bstr_t wrapper
    _bstr_t bstrWrapper;

    // creates BSTR and attaches to it
    bstrWrapper = "some text";
    wprintf_s(L"bstrWrapper = %s\n",
              static_cast<wchar_t*>(bstrWrapper));

    // bstrWrapper releases its BSTR
    BSTR bstr = bstrWrapper.Detach();
    wprintf_s(L"bstrWrapper = %s\n",
              static_cast<wchar_t*>(bstrWrapper));
    // "some text"
    wprintf_s(L"bstr = %s\n", bstr);

    bstrWrapper.Attach(SysAllocString(OLESTR("SysAllocedString")));
    wprintf_s(L"bstrWrapper = %s\n",
              static_cast<wchar_t*>(bstrWrapper));

    // assign a BSTR to our _bstr_t
    bstrWrapper.Assign(bstr);
    wprintf_s(L"bstrWrapper = %s\n",
              static_cast<wchar_t*>(bstrWrapper));

    // done with BSTR, do manual cleanup
    SysFreeString(bstr);

    // resuse bstr
    bstr= SysAllocString(OLESTR("Yet another string"));
    // two wrappers, one BSTR
    _bstr_t bstrWrapper2 = bstrWrapper;

    *bstrWrapper.GetAddress() = bstr;

    // bstrWrapper and bstrWrapper2 do still point to BSTR
    bstr = 0;
    wprintf_s(L"bstrWrapper = %s\n",
              static_cast<wchar_t*>(bstrWrapper));
    wprintf_s(L"bstrWrapper2 = %s\n",
              static_cast<wchar_t*>(bstrWrapper2));

    // new value into BSTR
    _snwprintf_s(bstrWrapper.GetBSTR(), 100, bstrWrapper.length(),
                 L"changing BSTR");
    wprintf_s(L"bstrWrapper = %s\n",
              static_cast<wchar_t*>(bstrWrapper));
    wprintf_s(L"bstrWrapper2 = %s\n",
              static_cast<wchar_t*>(bstrWrapper2));
}
```

```Output
bstrWrapper = some text
bstrWrapper = (null)
bstr = some text
bstrWrapper = SysAllocedString
bstrWrapper = some text
bstrWrapper = Yet another string
bstrWrapper2 = some text
bstrWrapper = changing BSTR
bstrWrapper2 = some text
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _bstr_t](../cpp/bstr-t-class.md)
