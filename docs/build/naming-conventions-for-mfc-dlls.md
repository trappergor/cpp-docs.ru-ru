---
title: "Соглашения об именовании библиотек DLL MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC libraries [C++], naming conventions
- naming conventions [C++], MFC DLLs
- MFC DLLs [C++], naming conventions
- libraries [C++], MFC DLL names
- shared DLL versions [C++]
- DLLs [C++], naming conventions
- DLLs [C++], library names
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f7702e9babcc4769136d6deab63b627f8b09bd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="naming-conventions-for-mfc-dlls"></a>Соглашения об именовании библиотек DLL в библиотеке MFC
Библиотеки DLL и библиотеки в библиотеке MFC выполните структурированных соглашение об именовании. Это упрощает знать, какие библиотеки DLL или библиотеки следует использовать для какой цели.  
  
 Импорт библиотеки, необходимые для построения приложений или библиотек DLL расширения MFC, использующих эти DLL-файлы имеют такое же базовое имя, что и библиотека DLL, но имеют расширение имени файла LIB-файл.  
  
### <a name="shared-dll-naming-convention"></a>Соглашение об именовании общей библиотеки DLL  
  
|DLL|Описание:|  
|---------|-----------------|  
|MFCx0.DLL|Библиотека DLL MFC, ANSI окончательной версии|  
|Библиотеку MFCx0U.DLL|Библиотека DLL MFC, версия Юникод для выпуска|  
|Версии MFCx0D.dll —|Библиотека DLL MFC, версия ANSI отладки|  
|MFCx0UD.DLL|Библиотека DLL MFC, отладочная версия Юникод|  
  
 Если динамически связываемых в общедоступную версию библиотеки DLL MFC, будь то из приложения или из библиотеки DLL расширения MFC, необходимо включить MFCx0.DLL с продуктом. Если требуется поддержка Юникода в приложении, включите библиотеку MFCx0U.DLL.  
  
 Если выполняется статическое связывание с MFC библиотеки DLL, необходимо связать его с помощью одного из статических библиотек MFC. Эти версии присваиваются в соответствии с соглашением [Н &#124; U] AFXCW [D]. LIB. Дополнительные сведения см. в таблице «Статическая соглашения об именовании библиотек» в [соглашения об именовании библиотек](../mfc/library-naming-conventions.md) (MFC).  
  
 Список библиотек DLL Visual C++, которые можно использовать с приложениями в файле Redist.txt в установку Visual Studio.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Соглашения об именовании библиотек](../mfc/library-naming-conventions.md)  
  
## <a name="see-also"></a>См. также  
 [DLL в Visual C++](../build/dlls-in-visual-cpp.md)