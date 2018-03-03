---
title: "Найдите путь, используемый Windows для размещения библиотеки DLL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- searching [C++], DLLs
- DLLs [C++], Windows search path
- Windows [C++], DLL search path
- known DLL searches [C++]
- locating DLLs
- finding DLLs
- search paths [C++]
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 53350ed473226c86dd4fefa93cff376a371dedf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="search-path-used-by-windows-to-locate-a-dll"></a>Путь поиска, используемый Windows для обнаружения библиотеки DLL
При связывании явными и неявными Windows сначала выполняет поиск «известных библиотек DLL», таких как Kernel32.dll и User32.dll. Windows выполняет поиск библиотек DLL в следующей последовательности:  
  
1.  Каталог, где находится исполняемый модуль текущего процесса.  
  
2.  Текущий каталог.  
  
3.  Системный каталог Windows. **GetSystemDirectory** функция получает путь каталога.  
  
4.  Каталог Windows. **GetWindowsDirectory** функция получает путь каталога.  
  
5.  Каталоги, указанные в переменной среды PATH.  
  
    > [!NOTE]
    >  Переменной среды LIBPATH не используется.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Неявное связывание с библиотекой DLL](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Как явной ссылки на библиотеку DLL](../build/linking-an-executable-to-a-dll.md#linking-explicitly)  
  
-   [Определение подходящего метода связывания](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="see-also"></a>См. также  
 [DLL в Visual C++](../build/dlls-in-visual-cpp.md)