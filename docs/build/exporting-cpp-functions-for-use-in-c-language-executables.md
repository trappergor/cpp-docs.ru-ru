---
title: Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
ms.openlocfilehash: 86d771f8dcb9ee1ef137b7766f249a1dda7257db
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426489"
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C

Если у вас есть функции в DLL, написанные на языке C++, необходимо получить доступ из модуля языка C, следует объявить эти функции с компоновкой C, а не C++. Если не указано иное, компилятор C++ использует C++ типобезопасный именования (также известный как декорирования имен) и C++, соглашения о вызовах, которые трудно реализовать из C.

Чтобы указать компоновкой, укажите `extern "C"` объявлениях функций. Пример:

```
extern "C" __declspec( dllexport ) int MyFunc(long parm1);
```

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из DLL с использованием DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)

- [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью объявления __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Декорированные имена](../build/reference/decorated-names.md)

- [Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)
