---
title: "Автоматическая компоновка версии библиотеки MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: defaultlib
dev_langs: C++
helpviewer_keywords:
- defaultlib in MFC
- automatic links [MFC]
- MFC libraries, linking to
- linking [MFC], automatic of MFC library version
- linking [MFC]
- linking [MFC], of MFC
- MFC libraries, versions
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ddc156d8518318a686796a25e89ee84a9a67ee59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="automatic-linking-of-mfc-library-version"></a>Автоматическая компоновка версии библиотеки MFC
В версиях до версии 3.0 (до Visual C++ версии 2.0) MFC приходилось вручную указать правильную версию библиотеки MFC в списке ввода библиотек для компоновщика. С MFC версии 3.0 и более поздней версии он больше не требуется вручную указывать версию библиотеки MFC. Вместо этого, файлы заголовков MFC автоматически определить правильную версию библиотеки MFC, в зависимости от значений, определенных с `#define`, такие как **_DEBUG** или **_UNICODE**. Добавить файлы заголовков MFC **/DEFAULTLIB** директивы для ссылок в определенной версии библиотеки MFC.  
  
 Например следующий фрагмент кода из AFX. Файл заголовка указывает компоновщику на необходимость ссылку в любом NAFXCWD. LIB или NAFXCW. LIB версии MFC, в зависимости от того, используется ли отладочная версия MFC:  
  
```c++
#ifndef _UNICODE 
#ifdef _DEBUG
#pragma comment(lib, "nafxcwd.lib")
#else
#pragma comment(lib, "nafxcw.lib")
#endif
#else
#ifdef _DEBUG
#pragma comment(lib, "uafxcwd.lib")
#else
#pragma comment(lib, "uafxcw.lib")
#endif
#endif
```  
  
 Файлы заголовков MFC также связать все необходимые библиотеки, включая библиотеки MFC, библиотеками Win32, библиотеки OLE, построенная образцы библиотеки OLE, ODBC библиотеки и т. д. Библиотеками Win32 включают Kernel32.Lib, User32.Lib и GDI32.Lib.  
  
## <a name="see-also"></a>См. также  
 [Версии библиотек MFC](../mfc/mfc-library-versions.md)

