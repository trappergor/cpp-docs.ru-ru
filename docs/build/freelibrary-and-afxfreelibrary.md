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
ms.openlocfilehash: 9c657bb0d583270f81658afa53f36b1be6a4fd4a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493266"
---
# <a name="freelibrary-and-afxfreelibrary"></a>Функции FreeLibrary и AfxFreeLibrary

Процессы, которые явно связываются с библиотекой DLL, вызывают функцию [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary) , если модуль DLL больше не нужен. Эта функция уменьшает счетчик ссылок модуля и, если счетчик ссылок равен нулю, отменяет его сопоставление с адресным пространством процесса.

В приложении MFC используйте [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) вместо `FreeLibrary` для выгрузки библиотеки DLL расширения MFC. Интерфейс (прототип функции) для `AfxFreeLibrary` совпадает с. `FreeLibrary`

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Функции LoadLibrary и AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [Функция GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>См. также

[Создание библиотек DLL C/C++ в Visual Studio](dlls-in-visual-cpp.md)<br/>
[FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
