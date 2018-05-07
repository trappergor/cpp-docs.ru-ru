---
title: Добавлены сведения о поддержки ATL мастером ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.atl.support
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 450021fd1ea05831f44dd5af7a9f1e39a9d6fc5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>Сведения о добавлении поддержки ATL мастером ATL
Когда вы [Добавление поддержки ATL в существующий исполняемый файл MFC или библиотеки DLL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual C++ выполняет следующие изменения в существующий проект MFC (в этом примере используется проект с именем `MFCEXE`):  
  
-   Добавляются два новых файла (IDL-файл и RGS-файл, используемый для регистрации сервера).  
  
-   В основное приложение заголовка и файл реализации (Mfcexe.h и Mfcexe.cpp) новый класс (производный от **CAtlMFCModule**) будет добавлен. Помимо нового класса, в код добавляется `InitInstance` для регистрации. Код также добавляется `ExitInstance` функции для объекта класса. В файле заголовка, и, наконец, два новых файла заголовка (Initguid.h и Mfcexe_i.c) включены в файл реализации, в объявлении и инициализации новый GUID для **CAtlMFCModule**-производного класса.  
  
-   Чтобы зарегистрировать сервер надлежащим образом, файл ресурсов проекта добавляется запись для нового RGS-файла.  
  
## <a name="notes-for-dll-projects"></a>Примечания для проектов DLL  
 При добавлении поддержки ATL в проект MFC DLL, вы увидите некоторые различия. Код добавляется **DLLRegisterServer** и **DLLUnregisterServer** функции для регистрации и отмены регистрации библиотеки DLL. Код также добавляется к [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) и [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).  
  
## <a name="see-also"></a>См. также  
 [Поддержка ATL в проект MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
