---
title: Функции LoadLibrary и AfxLoadLibrary | Документы Microsoft
ms.custom: ''
ms.date: 05/24/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- LoadLibrary
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc3be5d374995c657021952184794f146c37f4dc
ms.sourcegitcommit: d1f576a0f59678edc3d93508cf46485138332178
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753592"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>Функции LoadLibrary и AfxLoadLibrary

Обрабатывает вызов [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) (или [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) явной ссылкой на библиотеку DLL. Если функция выполняется успешно, он сопоставляет указанную библиотеку DLL в адресное пространство вызывающего процесса и возвращает дескриптор библиотеки DLL, который можно использовать с другими функциями для явного связывания — например, `GetProcAddress` и `FreeLibrary`.

`LoadLibrary` пытается найти библиотеку DLL с помощью того же метода поиска, который используется для неявного связывания. Если системе не удается найти библиотеку DLL или функция точки входа возвращает значение FALSE, `LoadLibrary` возвращает значение NULL. Если вызов `LoadLibrary` указан модуль DLL, который уже сопоставлен в адресное пространство вызывающего процесса, функция возвращает дескриптор библиотеки DLL и увеличивает счетчик ссылок модуля.

Если DLL имеет функцию точки входа, операционная система вызывает функцию в контексте потока, вызвавшего `LoadLibrary`. Функция точки входа не вызывается, если библиотека DLL уже присоединена к процессу, из-за предыдущего вызова `LoadLibrary` , имеющий нет соответствующего вызова `FreeLibrary` функции.

Для приложений MFC, которые загружают библиотека DLL-расширения MFC, мы рекомендуем использовать `AfxLoadLibrary` вместо `LoadLibrary`. `AfxLoadLibrary` обрабатывает синхронизацию потока перед вызовом метода `LoadLibrary`. Интерфейс (прототип функции) для `AfxLoadLibrary` совпадает со значением `LoadLibrary`.

Если не удалось загрузить библиотеку DLL, процесс может попытаться восстановить из-за ошибки. Например процесс может уведомить пользователя об ошибке и попросите пользователя, укажите другой путь к библиотеке DLL.

> [!IMPORTANT]  
> Не забудьте указать полный путь для всех библиотек DLL. Текущий каталог просматривается первой при загрузке файлов. Если не указать путь к файлу, может загрузить файл, который не является предполагаемым. Другой способ избежать этого — с помощью [/DEPENDENTLOADFLAG](../build/reference/dependentloadflag.md) компоновщика.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Неявное связывание с библиотекой DLL](../build/linking-an-executable-to-a-dll.md#linking-implicitly)

- [Определение подходящего метода связывания](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Порядок поиска библиотеки динамической компоновки](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)

- [Функции FreeLibrary и AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)

- [Функция GetProcAddress](../build/getprocaddress.md)

## <a name="see-also"></a>См. также

- [DLL в Visual C++](../build/dlls-in-visual-cpp.md)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)