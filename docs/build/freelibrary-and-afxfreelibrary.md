---
title: Функции FreeLibrary и AfxFreeLibrary | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs:
- C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6c7e498100a60a3d4c592c343cc86b5ee0a0ea
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713366"
---
# <a name="freelibrary-and-afxfreelibrary"></a>Функции FreeLibrary и AfxFreeLibrary

Процессы, которые явно связать вызов DLL [FreeLibrary](https://msdn.microsoft.com/library/windows/desktop/ms683152(v=vs.85).aspx) функционировать, когда модуль DLL больше не используется. Это функция уменьшает значение счетчика ссылок модуля и, если счетчик ссылок равен нулю, unmaps его из адресного пространства процесса.

В приложении MFC использовать [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) вместо `FreeLibrary` выгрузка библиотеки DLL расширения MFC. Интерфейс (прототип функции) для `AfxFreeLibrary` совпадает со значением `FreeLibrary`.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Неявное связывание с библиотекой DLL](../build/linking-an-executable-to-a-dll.md#linking-implicitly)

- [Определение подходящего метода связывания](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Функции LoadLibrary и AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)

- [Функция GetProcAddress](../build/getprocaddress.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](../build/dlls-in-visual-cpp.md)<br/>
[FreeLibrary](https://msdn.microsoft.com/library/windows/desktop/ms683152(v=vs.85).aspx)
[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)