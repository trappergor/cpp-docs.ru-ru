---
title: 'Практическое: Добавление поддержки диспетчера перезапуска | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b30491b2cb46ab0e8b25edc2d39e6616817c9b4
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42538730"
---
# <a name="how-to-add-restart-manager-support"></a>Практическое руководство. Добавление поддержки диспетчера перезапуска

Диспетчер перезапуска — это компонент, добавленный для Visual Studio для Windows Vista или более поздних операционных системах. Диспетчер перезапуска обеспечивает функции поддержки для приложения в случае его непредвиденного закрытия или перезапуска. Поведение диспетчера перезапуска зависит от типа приложения. Если приложение является редактором документов, то диспетчер перезапуска позволяет приложению автоматически сохранять состояние и содержимое всех открытых документов, а затем перезапускает приложение после непредвиденного закрытия. Если приложение не является редактором документов, диспетчер перезапуска перезапускает приложение, однако не может сохранить состояние приложения по умолчанию.  
  
 После перезапуска приложение выводит диалоговое окно задач (для Юникода). Если это приложение ANSI, оно выводит окно сообщения Windows. На этом этапе пользователь выбирает, нужно ли восстановить автоматически сохраненные документы. Если пользователь не восстанавливает автоматически сохраненные документы, диспетчер перезапуска удаляет временные файлы.  
  
> [!NOTE]
>  Поведение диспетчера перезапуска по умолчанию можно переопределить для сохранения данных и перезапуска приложения.  
  
 По умолчанию приложения MFC, созданные с помощью мастера проектов в Visual Studio поддерживают диспетчер перезапуска, когда приложения работают на компьютере с Windows Vista или более поздней версии операционной системы. Если поддержка диспетчера перезапуска в приложении не требуется, можно отключить диспетчер перезапуска в мастере создания проекта.  
  
### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>Добавление поддержки диспетчера перезапуска в существующее приложение  
  
1.  Откройте существующее приложение MFC в Visual Studio.  
  
2.  Откройте исходный файл для основного приложения. По умолчанию это CPP-файл, который имеет то же имя, что и приложение. Например, исходный файл основного приложения для MyProject — MyProject.cpp.  
  
3.  Найдите конструктор для основного приложения. Например, если проект — MyProject, конструктор имеет имя `CMyProjectApp::CMyProjectApp()`.  
  
4.  Добавьте следующий код в конструктор.  
  
 ```  
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;  
 ```  
  
5.  Убедитесь, что метод `InitInstance` приложения вызывает родительский метод `InitInstance` : [CWinApp::InitInstance](../mfc/reference/cwinapp-class.md#initinstance) или `CWinAppEx::InitInstance`. `InitInstance` Метод отвечает за проверку *m_dwRestartManagerSupportFlags* параметра.  
  
6.  Скомпилируйте и запустите приложение.  
  
## <a name="see-also"></a>См. также  
 [Класс CDataRecoveryHandler](../mfc/reference/cdatarecoveryhandler-class.md)   
 [CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)   
 [Класс CWinApp](../mfc/reference/cwinapp-class.md)   
 [CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)   
 [CDocument::OnDocumentEvent](../mfc/reference/cdocument-class.md#ondocumentevent)

