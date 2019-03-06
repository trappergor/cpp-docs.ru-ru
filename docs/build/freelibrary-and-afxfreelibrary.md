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
ms.openlocfilehash: 51d14b86a92f3acb76dc54d1bade2d2cd0baa055
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419957"
---
# <a name="freelibrary-and-afxfreelibrary"></a>Функции FreeLibrary и AfxFreeLibrary

Процессы, которые явно связать вызов DLL [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary) функционировать, когда модуль DLL больше не используется. Это функция уменьшает значение счетчика ссылок модуля и, если счетчик ссылок равен нулю, unmaps его из адресного пространства процесса.

В приложении MFC использовать [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) вместо `FreeLibrary` выгрузка библиотеки DLL расширения MFC. Интерфейс (прототип функции) для `AfxFreeLibrary` совпадает со значением `FreeLibrary`.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Неявное связывание с библиотекой DLL](../build/linking-an-executable-to-a-dll.md#linking-implicitly)

- [Определение подходящего метода связывания](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Функции LoadLibrary и AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)

- [Функция GetProcAddress](../build/getprocaddress.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](../build/dlls-in-visual-cpp.md)<br/>
[FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)
