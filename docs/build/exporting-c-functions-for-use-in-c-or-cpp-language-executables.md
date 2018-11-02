---
title: Экспорт функций на языке C для использования в исполняемых файлах, исходный код которых написан на языке C или C++
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
ms.openlocfilehash: 0b7347ee29e973e1043a153f8284baa47b674a4d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631821"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>Экспорт функций на языке C для использования в исполняемых файлах, исходный код которых написан на языке C или C++

При наличии функций в библиотеке DLL, написанные на языке C, необходимо получить доступ из модуля языка C++ или языка C, следует использовать **__cplusplus** макрос препроцессора, чтобы определить язык, который компилируется и затем объявите их функции с компоновкой C, если используется модуль на C++. Если вы используете этот метод и предоставить файлы заголовка для библиотеки DLL, эти функции могут использоваться пользователями C и C++ без изменения.

В следующем коде показано файл заголовка, который может использоваться клиентскими приложениями C и C++:

```h
// MyCFuncs.h
#ifdef __cplusplus
extern "C" {  // only need to export C interface if
              // used by C++ source code
#endif

__declspec( dllimport ) void MyCFunc();
__declspec( dllimport ) void AnotherCFunc();

#ifdef __cplusplus
}
#endif
```

Если вам необходимо связать функции C для исполняемого файла C++ и файлы заголовков объявление функции не использовали метод выше в файле исходного кода C++, выполните следующую команду, чтобы запретить компилятору выполнять Декорирование имен функций C:

```cpp
extern "C" {
#include "MyCHeader.h"
}
```

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из DLL с использованием DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)

- [Определение подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью объявления __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Декорированные имена](../build/reference/decorated-names.md)

- [Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)