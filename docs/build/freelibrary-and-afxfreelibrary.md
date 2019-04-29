---
title: Функции FreeLibrary и AfxFreeLibrary
ms.date: 11/04/2016
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
ms.openlocfilehash: 709e4fdbc24d6fbbac44944e686a6fecf8c9b8db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274044"
---
# <a name="freelibrary-and-afxfreelibrary"></a>Функции FreeLibrary и AfxFreeLibrary

Процессы, которые явно связать вызов DLL [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary) функционировать, когда модуль DLL больше не используется. Это функция уменьшает значение счетчика ссылок модуля и, если счетчик ссылок равен нулю, unmaps его из адресного пространства процесса.

В приложении MFC использовать [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) вместо `FreeLibrary` выгрузка библиотеки DLL расширения MFC. Интерфейс (прототип функции) для `AfxFreeLibrary` совпадает со значением `FreeLibrary`.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Функции LoadLibrary и AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [Функция GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](dlls-in-visual-cpp.md)<br/>
[FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
