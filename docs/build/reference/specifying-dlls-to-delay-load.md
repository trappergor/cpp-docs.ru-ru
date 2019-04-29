---
title: Задание библиотек DLL с отложенной загрузкой
ms.date: 11/04/2016
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
ms.openlocfilehash: 2b6737abd76c03186881e83bbd2bf286be6ffe2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318151"
---
# <a name="specifying-dlls-to-delay-load"></a>Задание библиотек DLL с отложенной загрузкой

Можно указать, какие библиотек DLL с отложенной загрузки с [/DELAYLOAD](delayload-delay-load-import.md):`dllname` параметр компоновщика. Если вы не планируете использовать собственную версию вспомогательной функции, необходимо также связать программу с библиотекой delayimp.lib (для классических приложений) или dloadhelper.lib (для приложений Магазина).

Ниже приведен простой пример задержки загрузки библиотеки DLL.

```
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll
#include <windows.h>
// uncomment these lines to remove .libs from command line
// #pragma comment(lib, "delayimp")
// #pragma comment(lib, "user32")

int main() {
   // user32.dll will load at this point
   MessageBox(NULL, "Hello", "Hello", MB_OK);
}
```

Создание ОТЛАДОЧНОЙ версии проекта. Просмотрите код, используя отладчик, и обратите внимание, что файл user32.dll загружается только при вызове `MessageBox`.

## <a name="see-also"></a>См. также

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](linker-support-for-delay-loaded-dlls.md)
