---
title: Функции LoadLibrary и AfxLoadLibrary
description: Использование LoadLibrary и AfxLoadLibrary для явной загрузки библиотек DLL в MSVC.
ms.date: 01/28/2020
f1_keywords:
- LoadLibrary
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
ms.openlocfilehash: f803212c4485f7517dc42802f1ff581ffa4e609d
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821542"
---
# <a name="loadlibrary-and-afxloadlibrary"></a>Функции LoadLibrary и AfxLoadLibrary

Процессы вызывают [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) или [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) для явной связи с библиотекой DLL. (Приложения MFC используют [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary) или [AfxLoadLibraryEx](../mfc/reference/application-information-and-management.md#afxloadlibraryex).) Если функция выполнена, она сопоставляет указанную библиотеку DLL с адресным пространством вызывающего процесса и возвращает дескриптор в библиотеку DLL. Этот дескриптор необходим в других функциях, используемых для явной компоновки, например `GetProcAddress` и `FreeLibrary`. Дополнительные сведения см. в разделе [Явные переопределения](linking-an-executable-to-a-dll.md#linking-explicitly).

`LoadLibrary` пытается найти библиотеку DLL с помощью той же последовательности поиска, которая используется для неявной компоновки. `LoadLibraryEx` обеспечивает более полный контроль над порядком пути поиска. Дополнительные сведения см. в разделе [Порядок поиска библиотеки динамической компоновки](/windows/win32/dlls/dynamic-link-library-search-order). Если системе не удается найти библиотеку DLL или функция точки входа возвращает значение FALSE, `LoadLibrary` возвращает значение NULL. Если в вызове `LoadLibrary` указан модуль DLL, который уже сопоставлен с адресным пространством вызывающего процесса, функция возвращает дескриптор библиотеки DLL и увеличивает счетчик ссылок модуля.

Если библиотека DLL имеет функцию точки входа, операционная система вызывает функцию в контексте потока, который вызывал `LoadLibrary` или `LoadLibraryEx`. Функция точки входа не вызывается, если библиотека DLL уже присоединена к процессу. Это происходит, если предыдущий вызов `LoadLibrary` или `LoadLibraryEx` для библиотеки DLL не имел соответствующего вызова функции `FreeLibrary`.

Для приложений MFC, которые загружают библиотеки DLL расширения MFC, рекомендуется использовать `AfxLoadLibrary` или `AfxLoadLibraryEx` вместо `LoadLibrary` или `LoadLibraryEx`. Функции MFC обработают синхронизацию потоков перед явной загрузкой библиотеки DLL. Интерфейсы (прототипы функций) для `AfxLoadLibrary` и `AfxLoadLibraryEx` совпадают с `LoadLibrary` и `LoadLibraryEx`.

Если Windows не удается загрузить библиотеку DLL, процесс может попытаться выполнить восстановление после ошибки. Например, он может уведомить пользователя об ошибке, а затем запросить другой путь к библиотеке DLL.

> [!IMPORTANT]
> Обязательно укажите полный путь к любым библиотекам DLL. Текущий каталог может быть просмотрен первым при загрузке файлов с `LoadLibrary`. Если вы указываете неполный путь к файлу, может быть загружен неправильный файл. При создании библиотеки DLL используйте параметр компоновщика [/DEPENDENTLOADFLAG](reference/dependentloadflag.md), чтобы указать порядок поиска для статически связываемых зависимостей DLL. В библиотеках DLL используйте оба полных пути для явно загруженных зависимостей и параметры вызовов `LoadLibraryEx` или `AfxLoadLibraryEx`, чтобы указать порядок поиска модулей. Дополнительные сведения см. в разделах [Безопасность библиотеки динамической компоновки (DLL)](/windows/win32/dlls/dynamic-link-library-security) и [Порядок поиска библиотеки динамической компоновки (DLL)](/windows/win32/dlls/dynamic-link-library-search-order).

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Порядок поиска библиотеки динамической компоновки (DLL)](/windows/win32/Dlls/dynamic-link-library-search-order)

- [Функции FreeLibrary и AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)

- [Функция GetProcAddress](getprocaddress.md)

## <a name="see-also"></a>См. также

- [Создание библиотек DLL C/C++ в Visual Studio](dlls-in-visual-cpp.md)
