---
title: "Поддержка библиотек динамической компоновки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- regular MFC DLLs [MFC], project targets as DLLs
- DLLs [MFC], MFC
- NAFXDW.LIB
- MFC DLLs [MFC], regular MFC DLLs
- USRDLLs, DLL support
- NAFXDWD.LIB
ms.assetid: cc31c69f-3c78-4db1-9ecd-0fd8dc3217e3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 394c48644c3b5cdc2514fefef2f4451e4098856f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dynamic-link-library-support"></a>Поддержка библиотек динамической компоновки
Библиотеки NAFXCW.lib и NAFXCWD.lib (перечисленных в таблице соглашения об именовании библиотек статическая в [соглашения об именовании библиотек](../mfc/library-naming-conventions.md)) создания проекта в виде библиотеки динамической компоновки, называется «Обычной DLL MFC» (ранее «USRDLL») который может использоваться с приложениями, которые не были включены библиотеки классов. Эта поддержка DLL не отличается от MFCx0.DLL и версии MFCx0D.dll — (известный как AFXDLL), которые содержат полную библиотеку классов в библиотеке DLL. Дополнительные сведения см. в разделе [DLL](../build/dlls-in-visual-cpp.md). Таблицу имен DLL, в разделе [соглашения об именовании библиотек DLL MFC](../build/naming-conventions-for-mfc-dlls.md).  
  
## <a name="see-also"></a>См. также  
 [Версии библиотек MFC](../mfc/mfc-library-versions.md)

