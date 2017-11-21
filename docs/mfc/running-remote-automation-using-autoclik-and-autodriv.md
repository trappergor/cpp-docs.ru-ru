---
title: "Выполнение удаленной автоматизации с помощью AUTOCLIK и AUTODRIV | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: AUTOCLIK sample [MFC]
ms.assetid: 8900c0de-8dba-4f0a-8d9e-7db77a1f4f46
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b48e542743642b2cd765150ea523da2cfe93f6dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="running-remote-automation-using-autoclik-and-autodriv"></a>Выполнение удаленной автоматизации с помощью AUTOCLIK и AUTODRIV
AUTOCLIK представляет простое приложение образец сервера автоматизации, которое можно использовать в качестве основы для получения дополнительных сведений о удаленной автоматизации. AUTODRIV представляет простое клиентское приложение автоматизации, которое управляет AUTOCLIK. Их можно использовать для демонстрации удаленной автоматизации.  
  
#### <a name="to-install-autoclikexe-on-two-machines-and-drive-it-using-remote-automation"></a>Чтобы установить AUTOCLIK. EXE-файла для двух компьютеров и управлять им с помощью удаленной автоматизации  
  
1.  Установка [AUTOCLIK](../visual-cpp-samples.md) образец приложения на компьютере разработки.  
  
2.  Построение AUTOCLIK. EXE-ФАЙЛА.  
  
3.  Запустите AUTOCLIK. Exe-ФАЙЛ в автономной среде способом и завершить его работу. Это будет зарегистрирован как сервера автоматизации.  
  
4.  Скопируйте AUTOCLIK. EXE-файла на удаленном компьютере, выполнить его там и завершить его работу.  
  
5.  Запустите AUTODRIV. Exe-ФАЙЛ на локальном компьютере и убедитесь, что его выполнение начинается AUTOCLIK. EXE-ФАЙЛА. Чтобы узнать больше о AUTODRIV. EXE-файла, в разделе [AUTOCLIK](../visual-cpp-samples.md).  
  
6.  На удаленном компьютере запустите AUTMGR32. EXE (диспетчер автоматизации).  
  
7.  На удаленном компьютере запустите RACMGR32. EXE (диспетчер подключений удаленной автоматизации).  
  
8.  В диспетчер подключений удаленной автоматизации, выберите AutoClik.Document из **классы OLE** списка.  
  
9. Выберите политику безопасности системы из **клиентского доступа** вкладку, чтобы предоставить доступ клиента к AutoClik.Document.  
  
10. Запустите RACMGR32 на локальном компьютере. Exe-ФАЙЛ и выберите AutoClik.Document из **классы OLE** списка.  
  
11. Из **соединение с сервером** выберите сетевой адрес удаленного компьютера и соответствующий сетевой протокол.  
  
12. С AutoClik.Document по-прежнему, выбранного в **классы OLE** полю со списком, выберите **удаленного** из `Register` меню.  
  
13. На локальном компьютере запустите AUTODRIV. Exe-ФАЙЛ или эквивалентные AUTOCLIK. Проект MAK Visual Basic, если вы хотите использовать Visual Basic, а не в MFC, клиента.  
  
 На удаленном компьютере теперь можно увидеть AUTOCLIK выполнения команд с помощью локального клиента.  
  
## <a name="see-also"></a>См. также  
 [Удаленная автоматизация](../mfc/remote-automation.md)

