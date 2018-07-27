---
title: 'Библиотек DLL, не являющихся MFC: Обзор | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c61ad8e6d1107dfdacc91c32d48ca1e3624a0211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368646"
---
# <a name="non-mfc-dlls-overview"></a>Общие сведения о библиотеках DLL, не являющихся MFC
Не - MFC библиотеки DLL является библиотекой DLL, внутренне не использует MFC, а экспортированные функции в DLL может быть вызван MFC или не MFC исполняемые файлы. Функции обычно экспортируются из не - MFC библиотеки DLL с помощью стандартного интерфейса C.  
  
 Дополнительные сведения о MFC DLL см. в разделе [библиотеки динамической компоновки](http://msdn.microsoft.com/library/windows/desktop/ms682589) в [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Пошаговое руководство: Создание и использование библиотеки DLL](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
  
-   [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)  
  
-   [Связывание исполняемого файла с библиотекой DLL](../build/linking-an-executable-to-a-dll.md)  
  
-   [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Обычные библиотеки DLL MFC, статически компонуемые с MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Обычные библиотеки DLL MFC, динамически компонуемые с MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Общие сведения о библиотеках DLL расширений MFC](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>См. также  
 [Типы библиотек DLL](../build/kinds-of-dlls.md)