---
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: 864236e86b4aeb6ce7b3315df57af1b577693c26
ms.sourcegitcommit: f127b08f114b8d6cab6b684febcb6f2ae0e055ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2019
ms.locfileid: "56954943"
---
# <a name="setcomerrorhandler"></a>_set_com_error_handler

**Блок, относящийся только к системам Microsoft**

Заменяет функцию по умолчанию, используемую для обработки ошибок COM.

## <a name="syntax"></a>Синтаксис

```
void __stdcall _set_com_error_handler(
   void (__stdcall *pHandler)(
      HRESULT hr,
      IErrorInfo* perrinfo
   )
);
```

#### <a name="parameters"></a>Параметры

*pHandler*<br/>
Указатель на функцию замены.

*hr*<br/>
Информация HRESULT.

*perrinfo*<br/>
Объект `IErrorInfo`.

## <a name="remarks"></a>Примечания

По умолчанию [_com_raise_error](../cpp/com-raise-error.md) обрабатывает все ошибки COM. Это поведение можно изменить с помощью **_set_com_error_handler** для вызова собственной функции обработки ошибок.

Функция замены должна иметь сигнатуру, эквивалентную сигнатуре `_com_raise_error`.

## <a name="example"></a>Пример

```cpp
// _set_com_error_handler.cpp
// compile with /EHsc
#include <stdio.h>
#include <comdef.h>
#include <comutil.h>

// Importing ado dll to attempt to establish an ado connection.
// Not related to _set_com_error_handler
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")

void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)
{
   throw "Unable to establish the connection!";
}

int main()
{
   _set_com_error_handler(_My_com_raise_error);
   _bstr_t bstrEmpty(L"");
   _ConnectionPtr Connection = NULL;
   try
   {
      Connection.CreateInstance(__uuidof(Connection));
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);
   }
   catch(char* errorMessage)
   {
      printf("Exception raised: %s\n", errorMessage);
   }

   return 0;
}
```

```Output
Exception raised: Unable to establish the connection!
```

## <a name="requirements"></a>Требования

**Заголовок:** \<comdef.h >

**LIB:** Если **/Zc: wchar_t** указан параметр компилятора (по умолчанию), используйте comsuppw.lib или comsuppwd.lib. Если **/Zc:wchar_t-** указан параметр компилятора, используйте comsupp.lib. Дополнительные сведения, включая задание этого параметра в интегрированной среде разработки, см. в разделе [/Zc: wchar_t (wchar_t — собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>См. также

[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)
