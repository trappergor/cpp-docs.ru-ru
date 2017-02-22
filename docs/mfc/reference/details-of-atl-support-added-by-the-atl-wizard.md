---
title: "Сведения о добавлении поддержки ATL мастером ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.atl.support"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, проекты MFC"
  - "MFC - библиотека, поддержка ATL"
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Сведения о добавлении поддержки ATL мастером ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При [добавлении поддержки ATL в существующий исполняемый файл или DLL MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) Visual C\+\+ выполняет в проекте MFC следующие изменения \(в данном примере используется проект с именем `MFCEXE`\):  
  
-   Добавляются два новых файла \(IDL\-файл и RGS\-файл, используемые для регистрации сервера\).  
  
-   В основные файлы заголовка и реализации приложения \(Mfcexe.h и Mfcexe.cpp\) добавляется новый класс \(полученный из **CAtlMFCModule**\).  Помимо нового класса добавляется код в функцию `InitInstance` для регистрации.  Добавляется также код в функцию `ExitInstance` для удаления объекта класса.  В файл реализации включаются два новых файла заголовка \(Initguid.h и Mfcexe\_i.c\), объявляющие и инициализирующие новые GUID для класса, производного от **CAtlMFCModule**.  
  
-   Чтобы зарегистрировать сервер надлежащим образом, в файл ресурсов проекта добавляется запись для нового RGS\-файла.  
  
## Примечания для проектов DLL  
 Процесс добавления поддержки ATL в проект DLL MFC имеет некоторые отличия.  В функции **DLLRegisterServer** и **DLLUnregisterServer** добавляется код для регистрации и отмены регистрации DLL.  Добавляется также код в функции [DllCanUnloadNow](../Topic/CAtlDllModuleT::DllCanUnloadNow.md) и [DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md).  
  
## См. также  
 [Поддержка ATL в проекте MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Добавление функции\-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной\-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)