---
title: Функции LoadLibrary и AfxLoadLibrary
ms.date: 05/24/2018
f1_keywords:
- LoadLibrary
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
ms.openlocfilehash: c7700dd865e320686a2ad8bd036f207b9ecee6ac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493207"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>Функции LoadLibrary и AfxLoadLibrary

Процессы вызывают [лоадлибрарекса](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) или [Лоадлибрарексв](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) (или [афкслоадлибрари](../mfc/reference/application-information-and-management.md#afxloadlibrary)) для явного связывания с библиотекой DLL. Если функция выполнена, она сопоставляет указанную библиотеку DLL с адресным пространством вызывающего процесса и возвращает в нее маркер, который можно использовать с другими функциями в явной компоновке, например `GetProcAddress` и. `FreeLibrary`

`LoadLibrary`пытается найти библиотеку DLL с помощью той же последовательности поиска, которая используется для неявной компоновки. Если системе не удается найти библиотеку DLL или если функция точки входа возвращает значение false, `LoadLibrary` возвращает значение null. Если при вызове `LoadLibrary` метода указан модуль DLL, который уже сопоставлен с адресным пространством вызывающего процесса, функция возвращает маркер библиотеки DLL и увеличивает счетчик ссылок модуля.

Если библиотека DLL имеет функцию точки входа, операционная система вызывает функцию в контексте потока, вызвавшего `LoadLibrary`. Функция точки входа не вызывается, если библиотека DLL уже присоединена к процессу из-за предыдущего вызова `LoadLibrary` , не имеющего соответствующего вызова `FreeLibrary` функции.

Для приложений MFC, которые загружают библиотеки DLL расширения MFC, рекомендуется использовать `AfxLoadLibrary` `LoadLibrary`вместо. `AfxLoadLibrary`обрабатывает синхронизацию потоков перед вызовом `LoadLibrary`. Интерфейс (прототип функции) `AfxLoadLibrary` `LoadLibrary`совпадает с.

Если Windows не удается загрузить библиотеку DLL, процесс может попытаться выполнить восстановление после ошибки. Например, процесс может уведомить пользователя об ошибке и попросить пользователя указать другой путь к библиотеке DLL.

> [!IMPORTANT]
> Обязательно укажите полный путь к любым библиотекам DLL. Текущий каталог сначала ищется при загрузке файлов. Если путь к файлу не указан, может быть загружен файл, который не является необходимым для загрузки. Другой способ избежать этого — использовать параметр компоновщика [/депендентлоадфлаг](reference/dependentloadflag.md) .

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Порядок поиска библиотек динамической компоновки](/windows/win32/Dlls/dynamic-link-library-search-order)

- [Функции FreeLibrary и AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [Функция GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>См. также

- [Создание библиотек DLL C/C++ в Visual Studio](dlls-in-visual-cpp.md)
