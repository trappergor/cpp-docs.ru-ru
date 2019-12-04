---
title: Ошибка компилятора C3345
ms.date: 11/04/2016
f1_keywords:
- C3345
helpviewer_keywords:
- C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
ms.openlocfilehash: e6962e5c127a92acc5dfdad580c7bc89fa134751
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753449"
---
# <a name="compiler-error-c3345"></a>Ошибка компилятора C3345

"идентификатор": недопустимый идентификатор для имени модуля

*Идентификатор* для модуля содержит как минимум один недопустимый символ. В правильном идентификаторе первым символом должна быть буква, подчеркивание или расширенный символ ANSI (0x80-FF), а все последующие символы должны быть буквами, цифрами, подчеркиваниями или расширенными символами ANSI.

### <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что *идентификатор* не содержит пробелы или другие недопустимые символы.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3345, поскольку параметр `name` атрибута `module` содержит пробел.

```cpp
// cpp_attr_name_module.cpp
// compile with: /LD /link /OPT:NOREF
#include <atlbase.h>
#include <atlcom.h>
#include <atlwin.h>
#include <atltypes.h>
#include <atlctl.h>
#include <atlhost.h>
#include <atlplus.h>

// C3345 expected
[module(dll, name="My Library", version="1.2", helpfile="MyHelpFile")]
// Try the following line instead
//[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]
// Module attribute now applies to this class
class CMyClass {
public:
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {
   // add your own code here
   return __super::DllMain(dwReason, lpReserved);
   }
};
```

## <a name="see-also"></a>См. также:

[__iscsym](../../c-runtime-library/reference/iscsym-functions.md)<br/>
[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[module](../../windows/module-cpp.md)
