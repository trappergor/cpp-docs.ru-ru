---
title: Экспорт из библиотеки DLL
ms.date: 11/04/2016
helpviewer_keywords:
- exporting DLLs [C++], about exporting from DLLs
- exporting functions [C++], DLLs (exporting from)
- exporting DLLs [C++]
- DLLs [C++], exporting from
- DLL exports [C++]
- functions [C++], exporting
- exports table [C++]
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
ms.openlocfilehash: 6bdf5b86724ae07aa073a9feb1cc4d5723bc6e6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196746"
---
# <a name="exporting-from-a-dll"></a>Экспорт из библиотеки DLL

DLL-файла имеет очень похожа на файл .exe с одним важным отличием — DLL-файл содержит таблицу экспорта. В таблице экспорта содержит имя каждой функции, библиотека DLL экспортирует в другие исполняемые файлы. Эти функции являются точками входа в библиотеку DLL. только функции в таблице экспорта может осуществляться другие исполняемые файлы. Другие функции в библиотеке DLL являются частными для библиотеки DLL. В таблице экспорта библиотеки DLL можно просмотреть с помощью [DUMPBIN](reference/dumpbin-reference.md) средство с параметром/EXPORTS.

Можно экспортировать функции из библиотеки DLL с помощью двух методов:

- Создание файла определения модуля (DEF) и использовать данный файл при построении библиотеки DLL. Используйте этот подход, если вы хотите [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).

- Используйте ключевое слово **__declspec(dllexport)** в определении функции.

При экспорте функции независимо от выбранного способа, обязательно используйте [__stdcall](../cpp/stdcall.md) соглашение о вызовах.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из DLL с использованием DEF-файлы](exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт и импорт с использованием AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Экспорт функций C++ для использования в исполняемых файлах языка C](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)

- [Определение подходящего метода экспорта для использования](determining-which-exporting-method-to-use.md)

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

- [Инициализация библиотеки DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Импорт в приложение](importing-into-an-application.md)

- [Импорт и экспорт встраиваемых функций](importing-and-exporting-inline-functions.md)

- [Взаимный импорт](mutual-imports.md)

## <a name="see-also"></a>См. также

[Импортирование и экспортирование](importing-and-exporting.md)
