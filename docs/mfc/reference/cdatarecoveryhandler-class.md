---
title: "CDataRecoveryHandler Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataRecoveryHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataRecoveryHandler class"
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataRecoveryHandler Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDataRecoveryHandler` autosaves документы и извлекает их если приложение неожиданно ".  
  
## Синтаксис  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## Члены  
  
### Конструкторы  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](../Topic/CDataRecoveryHandler::CDataRecoveryHandler.md)|Создает объект `CDataRecoveryHandler`.|  
  
### Методы  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveAllDocumentInfo.md)|Autosaves каждый файл, зарегистрированный с классом `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveDocumentInfo.md)|Autosaves указанный документ.|  
|[CDataRecoveryHandler::CreateDocumentInfo](../Topic/CDataRecoveryHandler::CreateDocumentInfo.md)|Добавляет документ в список открытых документов.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](../Topic/CDataRecoveryHandler::DeleteAllAutosavedFiles.md)|Удаляет все текущие autosaved файлы.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](../Topic/CDataRecoveryHandler::DeleteAutosavedFile.md)|Удаляет указанный autosaved файл.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](../Topic/CDataRecoveryHandler::GenerateAutosaveFileName.md)|Эта функция создает имя файла, связанного с предоставленным именем файла документа.|  
|[CDataRecoveryHandler::GetAutosaveInterval](../Topic/CDataRecoveryHandler::GetAutosaveInterval.md)|Возвращает интервал эта функция try.|  
|[CDataRecoveryHandler::GetAutosavePath](../Topic/CDataRecoveryHandler::GetAutosavePath.md)|Возвращает путь autosaved файлов.|  
|[CDataRecoveryHandler::GetDocumentListName](../Topic/CDataRecoveryHandler::GetDocumentListName.md)|Извлекает имя документа из объекта `CDocument`.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](../Topic/CDataRecoveryHandler::GetNormalDocumentTitle.md)|Восстанавливает обычное заголовок для заданного документа.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](../Topic/CDataRecoveryHandler::GetRecoveredDocumentTitle.md)|Создает и возвращает заголовок для восстановленного документа.|  
|[CDataRecoveryHandler::GetRestartIdentifier](../Topic/CDataRecoveryHandler::GetRestartIdentifier.md)|Извлекает уникальный идентификатор перезапуска приложения.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle.md)|Указывает, выполняет ли `CDataRecoveryHandler` эта функция в текущем цикле простоя.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](../Topic/CDataRecoveryHandler::GetShutdownByRestartManager.md)|Указывает, следует ли оставить вызвал диспетчер перезапуска приложения.|  
|[CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md)|Инициализирует объект `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::QueryRestoreAutosavedDocuments.md)|Отображает диалоговое окно для пользователя для каждого документа, `CDataRecoveryHandler` autosaved.  Диалоговое окно указывающее, стремится ли пользователь получить autosaved документ.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](../Topic/CDataRecoveryHandler::ReadOpenDocumentList.md)|Загружает список открытого документа из реестра.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](../Topic/CDataRecoveryHandler::RemoveDocumentInfo.md)|Удаляет указанный документ из списка открытого документа.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](../Topic/CDataRecoveryHandler::ReopenPreviousDocuments.md)|Открывает ранее открытые документы.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::RestoreAutosavedDocuments.md)|Извлекает autosaved документы, основанные на входе пользователя.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](../Topic/CDataRecoveryHandler::SaveOpenDocumentList.md)|Сохраняет текущий список открытых документов в реестр Windows.|  
|[CDataRecoveryHandler::SetAutosaveInterval](../Topic/CDataRecoveryHandler::SetAutosaveInterval.md)|Циклы эта функция задает время в миллисекундах.|  
|[CDataRecoveryHandler::SetAutosavePath](../Topic/CDataRecoveryHandler::SetAutosavePath.md)|Задает каталог, в котором хранятся файлы autosaved.|  
|[CDataRecoveryHandler::SetRestartIdentifier](../Topic/CDataRecoveryHandler::SetRestartIdentifier.md)|Задает уникальный идентификатор для этого экземпляра `CDataRecoveryHandler` перезапуска.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md)|Указывает, сохраняет ли `CDataRecoveryHandler` данные открытого документа в реестр Windows во время цикла текущим состояние бездействия.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](../Topic/CDataRecoveryHandler::SetShutdownByRestartManager.md)|Наборы было вызвано ли предыдущее выйти из приложения диспетчера перезапуска.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](../Topic/CDataRecoveryHandler::UpdateDocumentInfo.md)|Обновляет сведения для документа, поскольку пользователь сохранил его.|  
  
### Элементы данных  
  
|||  
|-|-|  
|m\_bRestoringPreviousOpenDocs|Указывает обнаруживает вновь ли обработчик восстановления данных ранее открытые документы.|  
|m\_bSaveDocumentInfoOnIdle|Указывает, что обработчик autosaves восстановления данных документы в следующем цикле простоя.|  
|m\_bShutdownByRestartManager|Указывает, вызывает ли диспетчер перезапуска приложения оставить.|  
|m\_dwRestartManagerSupportFlags|Пометит, указывающее, какая поддержка диспетчера перезапуска предоставляет для приложения.|  
|m\_lstAutosavesToDelete|Список autosaved файлов, которые не были удалены при подлинные документы были закрыты.  Когда приложение " диспетчер перезапуска повторная попытка удаления файлов.|  
|m\_mapDocNameToAutosaveName|Сопоставление имен документа в autosaved имена файлов.|  
|m\_mapDocNameToDocumentPtr|Сопоставление имен документа к указателям [CDocument](../Topic/CDocument%20Class.md).|  
|m\_mapDocNameToRestoreBool|Сопоставление имен документа в логический параметр, который указывает, является ли получить autosaved документ.|  
|m\_mapDocumentPtrToDocName|Сопоставление указателей `CDocument` к именам документа.|  
|m\_mapDocumentPtrToDocTitle|Сопоставление указателей на `CDocument` названиям документа.  Эти заголовки используются для сохранения файлов.|  
|m\_nAutosaveInterval|Время в миллисекундах autosaves.|  
|m\_nTimerID|Идентификатор таймера эта функция.|  
|m\_strAutosavePath|Местоположение, где autosaved документы сохраняются.|  
|m\_strRestartIdentifier|Строковое представление GUID диспетчера перезапуска.|  
  
## Заметки  
 Диспетчер перезапуска использует класс `CDataRecoveryHandler` для отслеживания всех открытых документов и эта функция их при необходимости.  Чтобы разрешить эта функция используется метод [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md).  Этот метод переводит `CDataRecoveryHandler` простоя для выполнения эта функция в следующем цикле.  Диспетчер перезапуска вызывает `SetSaveDocumentInfoOnIdle` при `CDataRecoveryHandler` должно выполняться эта функция.  
  
 Все методы класса `CDataRecoveryHandler` виртуальный.  Переопределите методы в этом классе позволяет создать собственный пользовательский механизм восстановления данных.  Если не создать собственный обработчик восстановления данных или перезапуска диспетчер, не создавайте CDataRecoveryHandler.  [CWinApp Class](../../mfc/reference/cwinapp-class.md) создает объект `CDataRecoveryHandler` по мере необходимости.  
  
 Прежде чем использовать объект `CDataRecoveryHandler`, необходимо вызвать [CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md).  
  
 Поскольку класс `CDataRecoveryHandler` закрыть подключение в диспетчер перезапуска, зависит от `CDataRecoveryHandler` глобальные параметры `m_dwRestartManagerSupportFlags`.  Этот параметр определяет, какие разрешения имеет диспетчер перезапуска и как он взаимодействует с приложением.  Чтобы включить диспетчер перезапуска в существующее приложение, необходимо присвоить `m_dwRestartManagerSupportFlags` соответствующее значение в конструкторе главной программы.  Дополнительные сведения об использовании диспетчера перезапуска см. в разделе [Практическое руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md).  
  
## Требования  
 **заголовок:** afxdatarecovery.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [Практическое руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)