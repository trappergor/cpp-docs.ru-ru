---
title: ConvertBSTRToString
ms.date: 11/04/2016
f1_keywords:
- ConvertBSTRToString
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
ms.openlocfilehash: df123dc218aa770a67536bf1bad7d8bafcf4c318
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522425"
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString

**Блок, относящийся только к системам Microsoft**

Преобразует `BSTR` значение `char *`.

## <a name="syntax"></a>Синтаксис

```
char* __stdcall ConvertBSTRToString(BSTR pSrc);
```

#### <a name="parameters"></a>Параметры

*pSrc*<br/>
Переменная BSTR.

## <a name="remarks"></a>Примечания

**ConvertBSTRToString** выделяет строку необходимо удалить.

## <a name="example"></a>Пример

```cpp
// ConvertBSTRToString.cpp
#include <comutil.h>
#include <stdio.h>

#pragma comment(lib, "comsuppw.lib")

int main() {
   BSTR bstrText = ::SysAllocString(L"Test");
   wprintf_s(L"BSTR text: %s\n", bstrText);

   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);
   printf_s("char * text: %s\n", lpszText2);

   SysFreeString(bstrText);
   delete[] lpszText2;
}
```

```Output
BSTR text: Test
char * text: Test
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:** \<comutil.h >

**LIB:** comsuppw.lib или comsuppwd.lib (см. в разделе [/Zc: wchar_t (wchar_t — собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Дополнительные сведения)

## <a name="see-also"></a>См. также

[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)