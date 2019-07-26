---
title: Предупреждение средств компоновщика LNK4217
ms.date: 07/23/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: 1301dd53f71c616d7b7af346923a54c42903c9fd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450862"
---
# <a name="linker-tools-warning-lnk4217"></a>Предупреждение средств компоновщика LNK4217

> символ "*symbol*", определенный в "*filename_1. obj*", импортируется "*filename_2. obj*" в функции "*Function*"

для символа указан [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) , хотя символ определен в объектном файле в том же образе. Чтобы устранить это предупреждение, удалите модификатор.`__declspec(dllimport)`

## <a name="remarks"></a>Примечания

*symbol* — это имя символа, определенное в изображении. *функция* — это функция, которая импортирует символ.

Это предупреждение не появляется при компиляции с параметром [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) .

LNK4217 также может возникнуть при попытке связать два модуля вместе, когда вместо этого следует компилировать второй модуль с помощью библиотеки импорта первого модуля.

```cpp
// main.cpp
__declspec(dllimport) void func();

int main()
{
    func();
    return 0;
}

```

Затем:

```cpp
// tt.cpp
// compile with: /c
void func() {}
```

Попытка скомпилировать эти два модуля, как показано ниже, приведет к LNK4217:

```cmd
cl.exe /c main.cpp tt.cpp
link.exe main.obj tt.obj
```

Чтобы устранить эту ошибку, после компиляции двух файлов передайте TT. obj в lib. exe, чтобы создать LIB-файл, а затем свяжите Main. obj с TT. lib, как показано ниже:

```cmd
cl.exe /c main.cpp tt.cpp
lib.exe tt.obj /export:func /def
link.exe main.obj tt.lib
```

## <a name="see-also"></a>См. также

[Предупреждение средств компоновщика LNK4049](linker-tools-warning-lnk4049.md) \
[Предупреждение средств компоновщика LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)