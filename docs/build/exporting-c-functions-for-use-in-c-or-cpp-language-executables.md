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
ms.openlocfilehash: 4dcf46e6bdde66a303afc2c4ec94fc8aefdd5e5d
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506640"
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>Экспорт функций на языке C для использования в исполняемых файлах, исходный код которых написан на языке C или C++

Если в библиотеке DLL, написанной на языке C, есть функции, к которым требуется получать доступ из модуля на языке C или C++, следует использовать макрос препроцессора **__cplusplus** для определения компилируемого языка, а затем объявить эти функции с компоновкой C, если они используются из модуля на языке C++. При использовании такого приема и предоставлении файлов заголовков для библиотеки DLL функции можно использовать как в C, так и в C++ без изменений.

В следующем коде показан файл заголовка, который может использоваться в клиентских приложениях как на C, так и на C++:

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

Если необходимо связать функции C с исполняемым файлом C++, но для файлов заголовков в объявлении функции не использовался описанный выше метод, в исходном файле C++ следует выполнить следующие действия, чтобы компилятор не декорировал имена функций на C:

```cpp
extern "C" {
#include "MyCHeader.h"
}
```

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из библиотеки DLL с использованием DEF-файлов](exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Определение подходящего способа экспорта](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Внутренние имена](reference/decorated-names.md)

- [Использование ключевого слова extern для задания компоновки](../cpp/extern-cpp.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
