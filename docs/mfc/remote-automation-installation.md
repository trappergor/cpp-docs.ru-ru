---
title: "Установка удаленной автоматизации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Remote Automation [MFC], installation
- installing Remote Automation [MFC]
ms.assetid: 9a02c9f6-dfc6-4489-b240-a1afe25fa0c5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acd8ee55261dfa03c68aef506dc90188d8d27d37
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="remote-automation-installation"></a>Установка удаленной автоматизации
Удаленная автоматизация содержит сравнительно мало компонента.  
  
-   Удаленная автоматизация клиентского прокси AUTPRX32. БИБЛИОТЕКИ DLL.  
  
-   Удаленная автоматизация серверный компонент, диспетчер автоматизации, AUTMGR32. EXE-ФАЙЛА.  
  
-   Диспетчер RAC RACMGR32. EXE-файла, с его RACREG32 сопоставления. БИБЛИОТЕКИ DLL.  
  
 Из этих RAC Manager записывается на языке Visual Basic и поэтому должен поддерживать времени выполнения Visual Basic. Эти и другие файлы удаленной автоматизации устанавливаются программой установки при установке Visual C++ Enterprise Edition.  
  
 При копировании компоненты удаленной автоматизации на компьютере, на какие версии Visual C++ Enterprise Edition не установлен, убедитесь, что REGSRV32. Exe-ФАЙЛ находится на пути компьютера, а также зарегистрировать RACREG32. Библиотеки DLL, используя следующую команду:  
  
 REGSRVR32 RACREG32. БИБЛИОТЕКИ DLL  
  
> [!NOTE]
>  Версии диспетчера RAC до Visual C++ 5.0 требуется GUAGE32. OCX и TABCTL32. OCX. Ни один из этих является обязательным для версией RAC Manager, которая поставляется с Visual C++ Enterprise Edition, 5.0 или более поздней версии.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Диспетчер автоматизации](../mfc/automation-manager-mfc.md)  
  
 [Диспетчер подключений удаленной автоматизации](../mfc/remote-automation-connection-manager.md)  
  
 [Пользовательские компоненты удаленной автоматизации](../mfc/remote-automation-user-components.md)  
  
## <a name="see-also"></a>См. также  
 [Удаленная автоматизация](../mfc/remote-automation.md)

