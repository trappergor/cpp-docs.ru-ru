---
title: Функции FreeLibrary и AfxFreeLibrary | Документы Microsoft
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
ms.openlocfilehash: f1e1bf5f1a05438ddf89af86c9b0d12e7885b901
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="freelibrary-and-afxfreelibrary"></a>Функции FreeLibrary и AfxFreeLibrary
Процессы, которые явно связать до вызова функции DLL [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188) работает, если модуль DLL больше не нужен. Это функция уменьшает значение счетчика ссылок модуля и, если счетчик ссылок равен нулю, отменяет сопоставление из адресного пространства процесса.  
  
 В приложении MFC использовать [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary) вместо `FreeLibrary` выгрузить DLL расширения MFC. Интерфейс (прототип функции) для `AfxFreeLibrary` совпадает со значением `FreeLibrary`.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Неявное связывание с библиотекой DLL](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Определение подходящего метода связывания](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Функции LoadLibrary и AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [Функция GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>См. также  
 [Библиотеки DLL в Visual C++](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)