---
title: Явная выгрузка библиотеки DLL, загруженной с задержкой
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
ms.openlocfilehash: f661694dd791ed8db3cd9f5b72a021c7470d17f3
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420457"
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>Явная выгрузка библиотеки DLL, загруженной с задержкой

[/Delay](../../build/reference/delay-delay-load-import-settings.md): unload-параметр компоновщика позволяет выгружать библиотеку DLL, загруженную с задержкой. По умолчанию, когда ваш код выгружает библиотеку DLL (с помощью/DELAY: unload и **__FUnloadDelayLoadedDLL2**), импорты, загружаемые с задержкой остаются в таблице адресов импорта (IAT). Тем не менее при использовании/DELAY: unload в командной строке компоновщика, вспомогательная функция будет поддерживать явную выгрузку DLL-библиотеки, сброс IAT в своем первоначальном виде; указатели становится неправильным будут перезаписаны. Поле является IAT [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) , содержащий адрес копии оригинальной IAT (если он существует).

## <a name="example"></a>Пример

### <a name="code"></a>Код

```
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD
#include <windows.h>
#include <delayimp.h>
#include "MyDll.h"
#include <stdio.h>

#pragma comment(lib, "delayimp")
#pragma comment(lib, "MyDll")
int main()
{
    BOOL TestReturn;
    // MyDLL.DLL will load at this point
    fnMyDll();

    //MyDLL.dll will unload at this point
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");

    if (TestReturn)
        printf_s("\nDLL was unloaded");
    else
        printf_s("\nDLL was not unloaded");
}
```

### <a name="comments"></a>Комментарии

Важные примечания на выгрузка библиотеки DLL с отложенной загрузкой.

- Можно найти реализацию **__FUnloadDelayLoadedDLL2** функции в файле \VC7\INCLUDE\DELAYHLP. CPP.

- Имя параметра **__FUnloadDelayLoadedDLL2** функции должно точно соответствовать (включая регистр) Библиотека импорта содержимое (которая также присутствует строка в таблице импорта на рисунке). Можно просмотреть содержимое библиотеки импорта с [DUMPBIN/DEPENDENTS](../../build/reference/dependents.md). Если требуется соответствие строк без учета регистра, можно обновить **__FUnloadDelayLoadedDLL2** для использования одного из строковых функций CRT или вызов Windows API.

См. в разделе [выгрузка библиотеки DLL с Delay-Loaded](../../build/reference/unloading-a-delay-loaded-dll.md) Дополнительные сведения.

## <a name="see-also"></a>См. также

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)
