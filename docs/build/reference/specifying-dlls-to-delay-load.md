---
title: Задание библиотек DLL с отложенной загрузкой | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e9becc0a686d3add5db140b239f1997f81a45be
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722583"
---
# <a name="specifying-dlls-to-delay-load"></a>Задание библиотек DLL с отложенной загрузкой

Можно указать, какие библиотек DLL с отложенной загрузки с [/DELAYLOAD](../../build/reference/delayload-delay-load-import.md):`dllname` параметр компоновщика. Если вы не планируете использовать собственную версию вспомогательной функции, необходимо также связать программу с библиотекой delayimp.lib (для классических приложений) или dloadhelper.lib (для приложений Магазина).

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

[Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)