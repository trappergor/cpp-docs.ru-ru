---
title: "Диспетчер подключений удаленной автоматизации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Automation clients [MFC], configuring for Remote Automation
- registry [MFC], remote Automation
- Automation servers [MFC], configuring for Remote Automation
- Remote Automation Connection Manager [MFC]
- Remote Automation [MFC], configuring client and server machines
- RAC Manager tool [MFC]
ms.assetid: 562eb7bc-f95c-46ad-ac97-f0dfa98362af
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f1a3085c92335aa6a2e0c5cd79cebb733688448a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="remote-automation-connection-manager"></a>Диспетчер подключений удаленной автоматизации
Чтобы настроить компьютеры клиента и сервера, необходимо внести изменения в реестр. Вместо этого вручную, используйте диспетчер подключений удаленной автоматизации (RAC) гораздо проще. Это средство RACMGR32. EXE-файла, а также RACREG32. Библиотеки DLL, должен быть скопирован для любого выбранного каталога. Поместив его в путь, он может выполняться из панели задач, с помощью выполнения. Кроме того можно создать ярлык для ее или поместить ссылку на него в меню «Пуск».  
  
 RACMGR32 на языке Visual Basic, и поэтому некоторые Visual Basic должен поддерживают библиотеки DLL. Эти файлы будут находиться в том же каталоге, что RACMGR32. EXE-файла на компакт-диске. Версии этих файлов, устанавливаемых программой установки для Visual C++ Enterprise Edition является эквивалентным или более поздней, чем те, которые поставляются вместе с Visual Basic Enterprise Edition 5.0. Программа установки Visual C++ копирует новые версии файлов Visual Basic в системном каталоге. Для Windows 9 x этот каталог обычно является C:\Windows\System. Для Windows NT и Windows 2000 это обычно C:\WINNT\system32. Программа установки также регистрирует эти файлы операционной системы. Вы можете удалить их из установки Visual Basic.  
  
## <a name="see-also"></a>См. также  
 [Диспетчер автоматизации (MFC)](../mfc/automation-manager-mfc.md)   
 [Пользовательские компоненты удаленной автоматизации](../mfc/remote-automation-user-components.md)   
 [Установка удаленной автоматизации](../mfc/remote-automation-installation.md)

