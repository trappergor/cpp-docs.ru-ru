---
title: "Класс CDataRecoveryHandler | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
dev_langs:
- C++
helpviewer_keywords:
- CDataRecoveryHandler class
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c2a99e32a88b8cb3f12d0961451025596886abb0
ms.lasthandoff: 02/24/2017

---
# <a name="cdatarecoveryhandler-class"></a>Класс CDataRecoveryHandler
`CDataRecoveryHandler` Преждевременном документы и восстанавливает их, если приложение неожиданно завершает работу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Создает объект `CDataRecoveryHandler`.|  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|Зарегистрирована каждого файла преждевременном `CDataRecoveryHandler` класса.|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|Преждевременном указанного документа.|  
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|Добавляет документ в список открытых документов.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|Удаляет все текущие файлы автоматически сохраненная.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|Удаляет указанный автоматически сохраненная файл.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|Создает имя для автоматического сохранения файла, связанного с указанного имени файла.|  
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Возвращает интервал между попытками автосохранения.|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Возвращает путь к файлам автоматически сохраненная.|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Получает имя документа из `CDocument` объекта.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Возвращает обычный title для указанного документа.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Создает и возвращает заголовок для восстановленного документа.|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Извлекает идентификатор уникального перезапуска приложения.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|Указывает, является ли `CDataRecoveryHandler` выполняет Автосохранение текущего цикла простоя.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Указывает, привело ли диспетчер перезапуска для выхода из приложения.|  
|[CDataRecoveryHandler::Initialize](#initialize)|Инициализирует объект `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|Отображает диалоговое окно для пользователя, для каждого документа, который `CDataRecoveryHandler` автоматически сохраненная. Диалоговое окно определяет ли пользователю нужно восстановить документ автоматически сохраненная.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Загружает список открытых документов из реестра.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Удаляет указанный документ из списка открытых документов.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Открытие ранее открытые документы.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|Восстанавливает документы автоматически сохраненная на основе ввода пользователя.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Сохраняет текущий список открытых документов в реестре Windows.|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Задает интервал между циклами автосохранения в миллисекундах.|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Задает каталог, в котором хранятся файлы автоматически сохраненная.|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Задает перезапуска уникальный идентификатор для этого экземпляра `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|Задает ли `CDataRecoveryHandler` сохраняет данные открытых документов в реестр Windows во время текущего цикла простоя.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Задает значение, указывающее предыдущих выхода приложения было вызвано диспетчером перезапуска.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Обновляет сведения о документа, так как он сохранен.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|Указывает, открывается ли обработчик восстановления данных, ранее открытые документы.|  
|m_bSaveDocumentInfoOnIdle|Указывает ли преждевременном обработчик данных восстановления документов следующего цикла простоя.|  
|m_bShutdownByRestartManager|Указывает, вызывает ли диспетчер перезапуска для выхода из приложения.|  
|m_dwRestartManagerSupportFlags|Предоставляет флаги, указывающие, что поддержка диспетчера перезапуска приложения.|  
|m_lstAutosavesToDelete|Список автоматически сохраненная файлы, которые не были удалены, когда исходные документы были закрыты. При выходе из приложения, повторные попытки диспетчера перезапуска, при удалении файлов.|  
|m_mapDocNameToAutosaveName|Сопоставление имен к именам файлов автоматически сохраненная документа.|  
|m_mapDocNameToDocumentPtr|Сопоставление имен документа [CDocument](../../mfc/reference/cdocument-class.md) указатели.|  
|m_mapDocNameToRestoreBool|Сопоставление имен логический параметр, который указывает на необходимость восстановить документ автоматически сохраненная документа.|  
|m_mapDocumentPtrToDocName|Карта `CDocument` указатели на имена документов.|  
|m_mapDocumentPtrToDocTitle|Карта `CDocument` указатели на заголовки документов. Эти заголовки используются для сохранения файлов.|  
|m_nAutosaveInterval|Время в миллисекундах между преждевременном.|  
|m_nTimerID|Идентификатор таймера автоматического сохранения.|  
|m_strAutosavePath|Расположение, где хранятся документы автоматически сохраненная.|  
|m_strRestartIdentifier|Строковое представление идентификатора GUID диспетчера перезапуска.|  
  
## <a name="remarks"></a>Примечания  
 Использует диспетчер перезапуска `CDataRecoveryHandler` класса следует отслеживать все открытые документы и сохранять их при необходимости. Чтобы включить Автосохранение, используйте [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) метод. Этот метод указывает `CDataRecoveryHandler` для выполнения следующего цикла простоя автосохранения. Диспетчер перезапуска вызовы `SetSaveDocumentInfoOnIdle` при `CDataRecoveryHandler` следует выполнять автосохранения.  
  
 Все методы `CDataRecoveryHandler` класса являются виртуальными. Необходимо переопределите методы этого класса для создания собственного обработчика восстановления пользовательских данных. Если создание обработчика восстановления данных и диспетчер перезапуска, не следует создавать экземпляры CDataRecoveryHandler. [Класс CWinApp](../../mfc/reference/cwinapp-class.md) создает `CDataRecoveryHandler` объекта, поскольку оно является обязательным.  
  
 Прежде чем использовать `CDataRecoveryHandler` объекта необходимо вызвать [CDataRecoveryHandler::Initialize](#initialize).  
  
 Поскольку `CDataRecoveryHandler` класс тесно подключен диспетчер перезапуска `CDataRecoveryHandler` зависит от глобального параметра `m_dwRestartManagerSupportFlags`. Этот параметр определяет, какие разрешения у диспетчера перезапуска и как она взаимодействует с приложением. Чтобы включить диспетчер перезапуска в существующее приложение, необходимо назначить `m_dwRestartManagerSupportFlags` соответствующее значение в конструкторе основного приложения. Дополнительные сведения об использовании диспетчера перезапуска см. в разделе [Практическое руководство: Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdatarecovery.h  
  
##  <a name="autosavealldocumentinfo"></a>CDataRecoveryHandler::AutosaveAllDocumentInfo  
 Зарегистрирована каждого файла преждевременном `CDataRecoveryHandler` класса.  
  
```  
virtual BOOL AutosaveAllDocumentInfo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `CDataRecoveryHandler` сохраненных документов; `FALSE` Если любой документ не был сохранен.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает `TRUE` , если нет документов, которые необходимо сохранить. Он также возвращает `TRUE` без сохранения документов, если получение `CWinApp` или `CDocManager` для приложения приводит к ошибке.  
  
 Чтобы использовать этот метод, либо `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` или `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL` должна быть задана в `m_dwRestartManagerSupportFlags`. В разделе [m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) для получения дополнительной информации.  
  
##  <a name="autosavedocumentinfo"></a>CDataRecoveryHandler::AutosaveDocumentInfo  
 Преждевременном указанного документа.  
  
```  
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,  
    BOOL bResetModifiedFlag = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на `CDocument` для сохранения.|  
|[in] `bResetModifiedFlag`|`TRUE`Указывает, что `CDataRecoveryHandler` рассматривает `pDocument` изменяться; `FALSE` указывает, что инфраструктура считает `pDocument` быть без изменений. Дополнительные сведения о влиянии этого флага см.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если заданы соответствующие флаги и `pDocument` является допустимым `CDocument` объекта.  
  
### <a name="remarks"></a>Примечания  
 Каждый `CDocument` объект имеет флаг, указывающий, если он изменился с момента последнего сохранения. Используйте [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) для определения состояния этого флага. Если `CDocument` не была изменена с момента последнего сохранения `AutosaveDocumentInfo` удаляет все файлы автоматически сохраненная для этого документа. Если документ был изменен с момента последнего сохранения, закрытия пользователю сохранить документ перед закрытием.  
  
> [!NOTE]
>  С помощью `bResetModifiedFlag` переход состояния документа без изменений может привести пользователя, все несохраненные данные. Если инфраструктура считает документа без изменений, закрыв не запрашивает пользователю сохранить.  
  
 Этот метод создает исключение с [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) макрос Если `pDocument` не является допустимым `CDocument` объекта.  
  
 Чтобы использовать этот метод, либо `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` или `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` должна быть задана в `m_dwRestartManagerSupportFlags`.   
  
##  <a name="cdatarecoveryhandler"></a>CDataRecoveryHandler::CDataRecoveryHandler  
 Создает объект `CDataRecoveryHandler`.  
  
```  
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,  
    int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `dwRestartManagerSupportFlags`|Указывает, какие параметры диспетчера перезапуска, поддерживаются.|  
|[in] `nAutosaveInterval`|Время между преждевременном. Этот параметр указывается в миллисекундах.|  
  
### <a name="remarks"></a>Примечания  
 Платформа MFC автоматически создает `CDataRecoveryHandler` для приложения при использовании **новый проект** мастера. Если настройка поведения восстановления данных или диспетчер перезапуска, не следует создавать `CDataRecoveryHandler` объекта.  
  
  
##  <a name="createdocumentinfo"></a>CDataRecoveryHandler::CreateDocumentInfo  
 Добавляет документ в список открытых документов.  
  
```  
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на `CDocument`. Этот метод создает сведения о документе для этого `CDocument`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод проверяет, может ли `pDocument` уже есть в списке документов, прежде чем добавить документ. Если `pDocument` уже есть в списке, этот метод удаляет автоматически сохраненная файлов, связанных с `pDocument`.  
  
 Чтобы использовать этот метод, либо `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` или `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` должна быть задана в `m_dwRestartManagerSupportFlags`. 
  
##  <a name="deleteallautosavedfiles"></a>CDataRecoveryHandler::DeleteAllAutosavedFiles  
 Удаляет все текущие файлы автоматически сохраненная.  
  
```  
virtual BOOL DeleteAllAutosavedFiles();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию всегда возвращает `TRUE`.  
  
##  <a name="deleteautosavedfile"></a>CDataRecoveryHandler::DeleteAutosavedFile  
 Удаляет указанный автоматически сохраненная файл.  
  
```  
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `strAutosavedFile`|Строка, содержащая имя файла автоматически сохраненная.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию всегда возвращают `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод не может удалить файл автоматически сохраненная, она сохраняет имя файла в списке. Деструктор `CDataRecoveryHandler` предпринимается попытка удалить каждый файл автоматически сохраненная, указанные в этом списке.  
  
##  <a name="generateautosavefilename"></a>CDataRecoveryHandler::GenerateAutosaveFileName  
 Создает имя для автоматического сохранения файла, связанного с указанного имени файла.  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strDocumentName`  
 Строка, содержащая имя документа. `GenerateAutosaveFileName`использует это имя документа для создания соответствующего имени файла автосохранения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя файла автосохранения, созданные из `strDocumentName`.  
  
### <a name="remarks"></a>Примечания  
 Имя каждого документа имеется взаимно-однозначное сопоставление с именем файла автосохранения.  
  
##  <a name="getautosaveinterval"></a>CDataRecoveryHandler::GetAutosaveInterval  
 Возвращает интервал между попытками автосохранения.  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Время в миллисекундах между Автосохранение предпринимает попытку подключения.  
  
##  <a name="getautosavepath"></a>CDataRecoveryHandler::GetAutosavePath  
 Возвращает путь к файлам автоматически сохраненная.  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расположение, где хранятся документы автоматически сохраненная.  
  
##  <a name="getdocumentlistname"></a>CDataRecoveryHandler::GetDocumentListName  
 Получает имя документа из `CDocument` объекта.  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на `CDocument`. `GetDocumentListName`Получает имя документа от этого `CDocument`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя документа из `pDocument`.  
  
### <a name="remarks"></a>Примечания  
 `CDataRecoveryHandler` Использует имя документа в качестве ключа в `m_mapDocNameToAutosaveName`, `m_mapDocNameToDocumentPtr`, и `m_mapDocNameToRestoreBool`. Включение этих параметров `CDataRecoveryHandler` для наблюдения за `CDocument` объекты, имя файла автосохранения и параметров автосохранения.  
  
##  <a name="getnormaldocumenttitle"></a>CDataRecoveryHandler::GetNormalDocumentTitle  
 Возвращает обычный title для указанного документа.  
  
```  
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на `CDocument`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обычный заголовок для указанного документа.  
  
### <a name="remarks"></a>Примечания  
 Обычный заголовок документа обычно — имя файла без пути документа. Это название в **имя файла** поле **Сохранить как** диалоговое окно.  
  
##  <a name="getrecovereddocumenttitle"></a>CDataRecoveryHandler::GetRecoveredDocumentTitle  
 Создает и возвращает заголовок для восстановленного документа.  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strDocumentTitle`  
 Обычный заголовок для документа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Название восстановленного документа.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию восстановленный документа отображается обычный название с **[восстановлен]** к нему. Восстановленные заголовок отображается для пользователя при `CDataRecoveryHandler` запросов пользователю восстановить автоматически сохраненная документов.  
  
##  <a name="getrestartidentifier"></a>CDataRecoveryHandler::GetRestartIdentifier  
 Извлекает идентификатор уникального перезапуска приложения.  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Перезапуск уникальный идентификатор.  
  
### <a name="remarks"></a>Примечания  
 Перезапуск идентификатор уникален для каждого выполнения приложения.  
  
 `CDataRecoveryHandler` Сохраняет информацию в реестре о документы, открытые в настоящий момент. Когда диспетчер перезапуска завершает работу приложения и перезапускает его, он передает идентификатор перезагрузки `CDataRecoveryHandler`. `CDataRecoveryHandler` Использует идентификатор перезапуска для получения списка ранее открытые документы. Это позволяет `CDataRecoveryHandler` попытаться найти и восстановить файлы автоматически сохраненная.  
  
##  <a name="getsavedocumentinfoonidle"></a>CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 Указывает, является ли `CDataRecoveryHandler` выполняет Автосохранение текущего цикла простоя.  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает `CDataRecoveryHandler` преждевременном на текущего цикла простоя; `FALSE` указывает, это не так.  
  
##  <a name="getshutdownbyrestartmanager"></a>CDataRecoveryHandler::GetShutdownByRestartManager  
 Указывает, привело ли диспетчер перезапуска для выхода из приложения.  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, что диспетчер перезапуска привело завершать работу; `FALSE` указывает, это не так.  
  
##  <a name="initialize"></a>CDataRecoveryHandler::Initialize  
 Инициализирует объект `CDataRecoveryHandler`.  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если инициализация прошла успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Процесс инициализации загружает путь для хранения файлов автосохранения из реестра. Если `Initialize` метод не удается найти этот каталог, или если путь является `NULL`, `Initialize` завершается неудачей и возвращает `FALSE`.  
  
 Используйте [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) изменить путь автосохранения после инициализации приложения `CDataRecoveryHandler`.  
  
 `Initialize` Метод также запускает таймер, чтобы отслеживать, когда происходит Далее автосохранения. Используйте [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) Чтобы изменить интервал автоматического сохранения после инициализации приложения `CDataRecoveryHandler`.  
  
##  <a name="queryrestoreautosaveddocuments"></a>CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 Отображает диалоговое окно для пользователя, для каждого документа, который `CDataRecoveryHandler` автоматически сохраненная. Диалоговое окно определяет ли пользователю нужно восстановить документ автоматически сохраненная.  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>Примечания  
 Если приложение имеет формат Юникода, этот метод отображает [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) для пользователя. В противном случае — платформа использует [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) для запроса у пользователя.  
  
 После `QueryRestoreAutosavedDocuments` собирает все ответы от пользователя, он сохраняет информацию в переменной-члена `m_mapDocNameToRestoreBool`. Этот метод не восстанавливается автоматически сохраненная документов.  
  
##  <a name="readopendocumentlist"></a>CDataRecoveryHandler::ReadOpenDocumentList  
 Загружает список открытых документов из реестра.  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, что `ReadOpenDocumentList` загрузки сведений для документа, по крайней мере один из реестра; `FALSE` указывает, был загружен без сведений о документе.  
  
### <a name="remarks"></a>Примечания  
 Эта функция загружает из реестра сведения открытый документ и сохраняет его в переменной-члена `m_mapDocNameToAutosaveName`.  
  
 После `ReadOpenDocumentList` загружает все данные удаляются из реестра сведения о документе.  
  
##  <a name="removedocumentinfo"></a>CDataRecoveryHandler::RemoveDocumentInfo  
 Удаляет указанный документ из списка открытых документов.  
  
```  
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на документ для удаления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `pDocument` был удален из списка. `FALSE` Если произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь закрывает документ, платформа использует этот метод, чтобы удалить его из списка открытых документов.  
  
 Если `RemoveDocumentInfo` не удается найти `pDocument` в список открытых документов, он не выполняет никаких действий и возвращает `TRUE`.  
  
 Для использования этого метода `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` должна быть задана в `m_dwRestartManagerSupportFlags`.   
  
##  <a name="reopenpreviousdocuments"></a>CDataRecoveryHandler::ReopenPreviousDocuments  
 Открытие ранее открытые документы.  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если хотя бы один документ был открыт; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод открывает последнего сохранения ранее открытые документы. Если документ не был сохранен или автоматически сохраненная, `ReopenPreviousDocuments` откроется пустой документ, основанный на шаблоне для этого типа файлов.  
  
 Для использования этого метода `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` должна быть задана в `m_dwRestartManagerSupportFlags`. Если этот параметр не задан, `ReopenPreviousDocuments` не выполняет никаких действий и возвращает `FALSE`.  
  
 Если нет документов, хранящихся в списке ранее открытые документы `ReopenPreviousDocuments` не выполняет никаких действий и возвращает `FALSE`.  
  
##  <a name="restoreautosaveddocuments"></a>CDataRecoveryHandler::RestoreAutosavedDocuments  
 Восстанавливает документы автоматически сохраненная на основе ввода пользователя.  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод восстанавливает успешно документов.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) для определения того, что документы пользователя требуется восстановить. Если пользователь решает не восстановить документ автоматически сохраненная `RestoreAutosavedDocuments` удаляет файл автосохранения. В противном случае — `RestoreAutosavedDocuments` автоматически сохраненная версия заменяет открытый документ.  
  
 Чтобы использовать этот метод, либо `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` или `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES` должна быть задана в `m_dwRestartManagerSupportFlags`.   
  
##  <a name="saveopendocumentlist"></a>CDataRecoveryHandler::SaveOpenDocumentList  
 Сохраняет текущий список открытых документов в реестре Windows.  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если нет открытых документов, чтобы сохранить или если они были успешно сохранены. `FALSE`Если имеются документы, чтобы сохранить в реестре, но они не были сохранены из-за ошибки.  
  
### <a name="remarks"></a>Примечания  
 Диспетчер перезапуска вызовы `SaveOpenDocumentList` когда приложение неожиданно завершает работу, или при выходе из обновления. При повторном запуске приложения используется [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) для получения списка открытых документов.  
  
 Этот метод сохраняет только список открытых документов. Метод [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) отвечает за сохранение самих документов.  
  
##  <a name="setautosaveinterval"></a>CDataRecoveryHandler::SetAutosaveInterval  
 Задает интервал между циклами автосохранения в миллисекундах.  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nAutosaveInterval`  
 Новый интервал автоматического сохранения в миллисекундах.  
  
##  <a name="setautosavepath"></a>CDataRecoveryHandler::SetAutosavePath  
 Задает каталог, в котором хранятся файлы автоматически сохраненная.  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `strAutosavePath`|Путь, где хранятся файлы автосохранения.|  
  
### <a name="remarks"></a>Примечания  
 Изменение каталога автосохранения не перемещает файлы автоматически сохраненная в настоящее время.  
  
##  <a name="setrestartidentifier"></a>CDataRecoveryHandler::SetRestartIdentifier  
 Задает перезапуска уникальный идентификатор для этого экземпляра `CDataRecoveryHandler`.  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `strRestartIdentifier`|Уникальный идентификатор диспетчера перезапуска.|  
  
### <a name="remarks"></a>Примечания  
 Диспетчер перезапуска записывает сведения об открытых документов в реестре. Эта информация сохраняется с идентификатором уникальный перезапуска как ключ. Из-за перезапуска идентификатор является уникальным для каждого экземпляра приложения, может неожиданно прекратить работу нескольких экземпляров приложения и диспетчером перезапуска можно восстановить каждый из них.  
  
##  <a name="setsavedocumentinfoonidle"></a>CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 Задает ли `CDataRecoveryHandler` сохраняет данные открытых документов в реестр Windows во время текущего цикла простоя.  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `bSaveOnIdle`|`TRUE`для сохранения сведений о документе в течение текущего цикла простоя; `FALSE to not perform a save`.|  
  
##  <a name="setshutdownbyrestartmanager"></a>CDataRecoveryHandler::SetShutdownByRestartManager  
 Задает значение, указывающее предыдущих выхода приложения было вызвано диспетчером перезапуска.  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `bShutdownByRestartManager`|`TRUE`Чтобы указать, что диспетчер перезапуска привело завершать работу; `FALSE` для указания, что выхода из приложения по другой причине.|  
  
### <a name="remarks"></a>Примечания  
 Платформа ведет себя по-разному на основе предыдущих выхода непредвиденное или она была начата с диспетчером перезапуска.  
  
##  <a name="updatedocumentinfo"></a>CDataRecoveryHandler::UpdateDocumentInfo  
 Обновляет сведения о документа, так как он сохранен.  
  
```  
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на сохраненный документ.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод удалить автоматически сохраненная документ и обновить сведения о документе; `FALSE` Если произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь сохраняет документ, приложение удаляет файл автоматически сохраненная, поскольку он больше не нужен. `UpdateDocumentInfo`Удаляет файл автоматически сохраненная путем вызова [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo). `UpdateDocumentInfo`добавляет информацию из `pDocument` в список в настоящее время открытия документов, так как `RemoveDocumentInfo` удаляет эти сведения, а сохраненные документ еще открыт.  
  
 Для использования этого метода `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` должна быть задана в `m_dwRestartManagerSupportFlags`.   
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Практическое руководство: Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)


