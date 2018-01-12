---
title: "Функции FreeLibrary и AfxFreeLibrary | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs: C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d5f2c1cce980f97e7a99ff2347daceac05f984f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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