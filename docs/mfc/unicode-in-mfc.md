---
title: "Юникод в MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- wide characters, Unicode
- Unicode [MFC], MFC
- wide characters, encoding
- strings [MFC], Unicode
- Unicode [MFC], enabling
ms.assetid: 1002004b-4113-4380-bf63-e1570934b793
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bc7ac9a55818022a4238565ed4309fe96f7ec058
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="unicode-in-mfc"></a>Юникод в MFC
MFC поддерживает стандарт Юникод для кодирования расширенных символов на платформах Windows NT, Windows 2000 и Windows XP. Приложения на базе Юникода нельзя запускать на платформах Windows 98.  
  
 Ниже описаны Юникода версии библиотеки MFC  
  
### <a name="static-link-libraries"></a>Статическая компоновка библиотеки  
  
|Release|Отладка|Описание|  
|-------------|-----------|-----------------|  
|UAFXCW.lib, PDB-файл|UAFXCWD.lib, PDB-файл|Статическая компоновка библиотеки MFC в кодировке Юникод|  
  
### <a name="dynamic-link-libraries"></a>Библиотеки динамической компоновки  
  
|Release|Отладка|Описание|  
|-------------|-----------|-----------------|  
|MFC100U.lib, .dbg, def, .dll, .map, PDB-файл, .prf|MFC100UD.lib, .def, .dll, .map, PDB-файл|Библиотека импорта MFC в кодировке Юникод (см. примечания ниже описание расширения файла)|  
|MFCS100U.lib, PDB-файл|MFCS100UD.lib, PDB-файл|MFC Юникода импортировать библиотеку, содержащую код, который должен быть статически связывается приложения или DLL|  
  
 **Типы файлов**  
  
-   Импорт библиотеки файлы имеют расширение (.lib).  
  
-   Библиотека динамической компоновки файлы имеют расширение (.dll).  
  
-   Файлы модуля определения (DEF), текстовые файлы, содержащие инструкции для определения .exe или .dll.  
  
-   Файлы сопоставления (.map), текстовые файлы, содержащие данные, используемые компоновщиком при компоновке программы.  
  
-   Файлы библиотеки (LIB) используются в сочетании с версии библиотеки DLL MFC. Эти файлы содержат код, который должен быть статически связывается приложением или библиотекой DLL.  
  
-   Программа PDB-файлы содержат сведения о состоянии отладки и проекта.  
  
-   Файлы отладки (.dbg) содержат сведения (COFF FPO и CodeView), использующий отладчик Visual C++.  
  
 Подробные сведения о соглашениях об именах см. в разделе [соглашения об именовании библиотек](../mfc/library-naming-conventions.md).  
  
 Сведения об использовании Юникода с MFC см. в разделе [строк: задать многобайтовых символов (MBCS) поддержка Юникода и](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)

