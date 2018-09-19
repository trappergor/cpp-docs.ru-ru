---
title: _set_com_error_handler | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 192707fe15560adb816b530ecf0e67713ae7d302
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092561"
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

**LIB:** Если **wchar_t — собственный тип** включен параметр компилятора, используйте comsuppw.lib или comsuppwd.lib. Если **wchar_t — собственный тип** отключен, используйте comsupp.lib. Дополнительные сведения см. в разделе [/Zc:wchar_t (wchar_t — это собственный тип)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>См. также

[Глобальные функции COM-модели компилятора](../cpp/compiler-com-global-functions.md)