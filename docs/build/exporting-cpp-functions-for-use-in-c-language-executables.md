---
title: Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
ms.openlocfilehash: 38b13c1fc9c57354ba8160f6dbe0df6546fe7b5f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506604"
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C

При наличии функций в библиотеке DLL, написанной на C++, к которой необходимо получить доступ из модуля языка C, следует объявить эти функции с компоновкой C, а не с компоновкой C++. Если не указано иное, компилятор C++ использует строго типизированное именование C++ (также называемое внутренним именованием) и соглашения о вызовах C++, которые может оказаться сложно вызывать из C.

Чтобы указать компоновку C, укажите `extern "C"` для объявлений функций. Пример:

```
extern "C" __declspec( dllexport ) int MyFunc(long parm1);
```

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из библиотеки DLL с использованием DEF-файлов](exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Экспорт функций на языке C для использования в исполняемых файлах, исходный код которых написан на языке C или C++](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение подходящего способа экспорта](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Внутренние имена](reference/decorated-names.md)

- [Использование ключевого слова extern для задания компоновки](../cpp/extern-cpp.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
