---
title: Функции LoadLibrary и AfxLoadLibrary | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: bc4e211259e6c0a483f73094c442c034cd649616
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="loadlibrary-and-afxloadlibrary"></a>Функции LoadLibrary и AfxLoadLibrary
Обрабатывает вызов [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187) (или [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)) явной ссылкой на библиотеку DLL. Если функция выполняется успешно, он сопоставляет указанную библиотеку DLL в адресное пространство вызывающего процесса и возвращает дескриптор библиотеки DLL, который можно использовать с другими функциями для явного связывания — например, `GetProcAddress` и `FreeLibrary`.  
  
 `LoadLibrary` пытается найти библиотеку DLL с помощью того же метода поиска, который используется для неявного связывания. Если системе не удается найти библиотеку DLL или функция точки входа возвращает значение FALSE, `LoadLibrary` возвращает значение NULL. Если вызов `LoadLibrary` указан модуль DLL, который уже сопоставлен в адресное пространство вызывающего процесса, функция возвращает дескриптор библиотеки DLL и увеличивает счетчик ссылок модуля.  
  
 Если DLL имеет функцию точки входа, операционная система вызывает функцию в контексте потока, вызвавшего `LoadLibrary`. Функция точки входа не вызывается, если библиотека DLL уже присоединена к процессу, из-за предыдущего вызова `LoadLibrary` , имеющий нет соответствующего вызова `FreeLibrary` функции.  
  
 Для приложений MFC, которые загружают библиотека DLL-расширения MFC, мы рекомендуем использовать `AfxLoadLibrary` вместо `LoadLibrary`. `AfxLoadLibrary` обрабатывает синхронизацию потока перед вызовом метода `LoadLibrary`. Интерфейс (прототип функции) для `AfxLoadLibrary` совпадает со значением `LoadLibrary`.  
  
 Если не удалось загрузить библиотеку DLL, процесс может попытаться восстановить из-за ошибки. Например процесс может уведомить пользователя об ошибке и попросите пользователя, укажите другой путь к библиотеке DLL.  
  
> [!IMPORTANT]
>  Не забудьте указать полный путь для всех библиотек DLL. Текущий каталог просматривается первой при загрузке файлов. Если не указать путь к файлу, может загрузить файл, который не является предполагаемым.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Неявное связывание с библиотекой DLL](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Определение подходящего метода связывания](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Путь поиска, используемый Windows для размещения библиотеки DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [Функции FreeLibrary и AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [Функция GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>См. также  
 [Библиотеки DLL в Visual C++](../build/dlls-in-visual-cpp.md)   
 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187)   
 [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)