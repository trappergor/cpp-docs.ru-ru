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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 26e36977a2e18dcaa4a76b201f9543e200f2d276
ms.lasthandoff: 03/31/2017

---
# <a name="cdatarecoveryhandler-class"></a>Класс CDataRecoveryHandler
`CDataRecoveryHandler` Преждевременном документы и восстанавливает их при прекращении работы приложения.  
  
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
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Возвращает интервал между попытками эта функция.|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Возвращает путь к файлам автоматически сохраненная.|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Извлекает имя документа из `CDocument` объекта.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Извлекает обычного заголовка в указанном документе.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Создает и возвращает заголовок для восстановленного документа.|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Извлекает идентификатор уникальный перезапуска приложения.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|Указывает, является ли `CDataRecoveryHandler` выполняет эта функция для текущего цикла простоя.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Указывает, привело ли диспетчер перезапуска на выход из приложения.|  
|[CDataRecoveryHandler::Initialize](#initialize)|Инициализирует объект `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|Отображает диалоговое окно для пользователя, для каждого документа, `CDataRecoveryHandler` автоматически сохраненная. Диалоговое окно определяет ли пользователю необходимо восстановить автоматически сохраненная документ.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Загружает список открытых документов из реестра.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Удаляет указанный документ из списка открытых документов.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Открывает ранее открытых документов.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|Восстанавливает автоматически сохраненная документов на основе ввода пользователя.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Сохраняет текущий список открытых документов в реестре Windows.|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Задает интервал между циклами автосохранения в миллисекундах.|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Задает каталог, в которой хранятся файлы автоматически сохраненная.|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Задает перезапуск уникальный идентификатор для этого экземпляра `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|Задает ли `CDataRecoveryHandler` сохраняет сведения о открытый документ в реестр Windows в течение текущего цикла простоя.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Задает ли предыдущих выхода приложения была вызвана диспетчера перезапуска.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Обновляет данные о документа, так как он сохраненные пользователем.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|Указывает, открывается ли обработчик восстановления данных ранее открытых документов.|  
|m_bSaveDocumentInfoOnIdle|Указывает ли следующего цикла простоя документами преждевременном обработчик восстановления данных.|  
|m_bShutdownByRestartManager|Указывает, вызывает ли диспетчер перезапуска на выход из приложения.|  
|m_dwRestartManagerSupportFlags|Предоставляет флаги, указывающие, что поддержка диспетчера перезапуска для приложения.|  
|m_lstAutosavesToDelete|Список автоматически сохраненная файлы, которые не были удалены, когда были закрыты исходные документы. Когда приложение завершает работу, повторные попытки диспетчера перезапуска, при удалении файлов.|  
|m_mapDocNameToAutosaveName|Карта имен к именам файлов автоматически сохраненная документа.|  
|m_mapDocNameToDocumentPtr|Карта имен документа [CDocument](../../mfc/reference/cdocument-class.md) указатели.|  
|m_mapDocNameToRestoreBool|Сопоставление имен документов для логического параметра, который указывает, следует ли восстановить автоматически сохраненная документ.|  
|m_mapDocumentPtrToDocName|Карта `CDocument` указатели на имена документов.|  
|m_mapDocumentPtrToDocTitle|Карта `CDocument` указатели на заголовки документов. Эти заголовки используются для сохранения файлов.|  
|m_nAutosaveInterval|Время в миллисекундах между преждевременном.|  
|m_nTimerID|Идентификатор для автосохранения таймера.|  
|m_strAutosavePath|Расположение, где хранятся документы автоматически сохраненная.|  
|m_strRestartIdentifier|Строковое представление идентификатора GUID диспетчера перезапуска.|  
  
## <a name="remarks"></a>Примечания  
 Использует диспетчер перезапуска `CDataRecoveryHandler` класса следует отслеживать все открытые документы и сохранять их при необходимости. Чтобы включить автосохранения, используйте [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) метод. Этот метод направляет `CDataRecoveryHandler` для выполнения следующего цикла простоя эта функция. Диспетчер перезапуска вызовы `SetSaveDocumentInfoOnIdle` при `CDataRecoveryHandler` следует выполнять эта функция.  
  
 Все методы `CDataRecoveryHandler` класса являются виртуальными. Необходимо переопределите методы этого класса для создания обработчиком восстановления пользовательских данных. Если вы создаете собственный обработчик восстановления данных или диспетчер перезапуска, не следует создавать экземпляры CDataRecoveryHandler. [CWinApp-класс](../../mfc/reference/cwinapp-class.md) создает `CDataRecoveryHandler` объекта при необходимости.  
  
 Прежде чем использовать `CDataRecoveryHandler` объекта, необходимо вызвать [CDataRecoveryHandler::Initialize](#initialize).  
  
 Поскольку `CDataRecoveryHandler` класс тесно подключается диспетчер перезапуска `CDataRecoveryHandler` зависит от глобального параметра `m_dwRestartManagerSupportFlags`. Этот параметр определяет, какие разрешения, которые диспетчер перезапуска и его взаимодействия с приложением. Чтобы включить диспетчер перезапуска в существующее приложение, необходимо назначить `m_dwRestartManagerSupportFlags` соответствующее значение в конструкторе объекта основного приложения. Дополнительные сведения об использовании диспетчера перезапуска см. в разделе [как: Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md).  
  
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
 Этот метод возвращает `TRUE` , если нет документов, которые необходимо сохранить. Он также возвращает `TRUE` без сохранения всех документов, если получение `CWinApp` или `CDocManager` приложение создает ошибку.  
  
 С помощью этого метода, либо `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` или `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL` должна быть задана в `m_dwRestartManagerSupportFlags`. В разделе [m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) для получения дополнительной информации.  
  
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
|[in] `bResetModifiedFlag`|`TRUE`Указывает, что `CDataRecoveryHandler` рассматривает `pDocument` изменяемой; `FALSE` указывает, что инфраструктура считает `pDocument` быть без изменений. Дополнительные сведения о влиянии этого флага см.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если заданы соответствующие флаги и `pDocument` является допустимым `CDocument` объекта.  
  
### <a name="remarks"></a>Примечания  
 Каждый `CDocument` объект имеет флаг, указывающий, если она была изменена с момента последнего сохранения. Используйте [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) для определения состояния этого флага. Если `CDocument` не изменились с момента последнего сохранения `AutosaveDocumentInfo` удаляет все файлы автоматически сохраненная для этого документа. Если документ был изменен с момента последнего сохранения, закрытия пользователю сохранить документ перед закрытием.  
  
> [!NOTE]
>  С помощью `bResetModifiedFlag` для изменения состояния документа без изменений для чего пользователь может потерять несохраненные данные. Если платформа считает, что документ без изменений, закрытие, он не запрашивает пользователю сохранить.  
  
 Этот метод создает исключение с [ASSERT](diagnostic-services.md#assert) макрос Если `pDocument` не является допустимым `CDocument` объекта.  
  
 С помощью этого метода, либо `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` или `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` должна быть задана в `m_dwRestartManagerSupportFlags`.   
  
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
|[in] `dwRestartManagerSupportFlags`|Указывает, какие параметры диспетчера перезапуска поддерживаются.|  
|[in] `nAutosaveInterval`|Время между преждевременном. Этот параметр указывается в миллисекундах.|  
  
### <a name="remarks"></a>Примечания  
 Платформа MFC автоматически создает `CDataRecoveryHandler` для приложения при использовании **новый проект** мастера. Если вы настраиваете поведение при восстановлении данных или диспетчер перезапуска, не следует создавать `CDataRecoveryHandler` объекта.  
  
  
##  <a name="createdocumentinfo"></a>CDataRecoveryHandler::CreateDocumentInfo  
 Добавляет документ в список открытых документов.  
  
```  
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на `CDocument`. Этот метод создает сведения о документе для данного `CDocument`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод проверяет, если `pDocument` уже включен в список документов, прежде чем добавить документ. Если `pDocument` уже включен в список, этот метод удаляет автоматически сохраненная файлов, связанных с `pDocument`.  
  
 С помощью этого метода, либо `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` или `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` должна быть задана в `m_dwRestartManagerSupportFlags`. 
  
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
 Если этот метод не может удалить файл автоматически сохраненная, она сохраняет имя файла в список. Деструктор `CDataRecoveryHandler` предпринимается попытка удалить каждого автоматически сохраненная файл, указанный в этом списке.  
  
##  <a name="generateautosavefilename"></a>CDataRecoveryHandler::GenerateAutosaveFileName  
 Создает имя для автоматического сохранения файла, связанного с указанного имени файла.  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strDocumentName`  
 Строка, содержащая имя документа. `GenerateAutosaveFileName`использует это имя документа, для создания соответствующего имени файла автосохранения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя файла автосохранения, созданные из `strDocumentName`.  
  
### <a name="remarks"></a>Примечания  
 Имя каждого документа имеется взаимно-однозначное сопоставление с именем файла, эта функция.  
  
##  <a name="getautosaveinterval"></a>CDataRecoveryHandler::GetAutosaveInterval  
 Возвращает интервал между попытками эта функция.  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Время в миллисекундах между эта функция пытается подключиться.  
  
##  <a name="getautosavepath"></a>CDataRecoveryHandler::GetAutosavePath  
 Возвращает путь к файлам автоматически сохраненная.  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Расположение, где хранятся документы автоматически сохраненная.  
  
##  <a name="getdocumentlistname"></a>CDataRecoveryHandler::GetDocumentListName  
 Извлекает имя документа из `CDocument` объекта.  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на `CDocument`. `GetDocumentListName`Извлекает имя документа из этого `CDocument`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя документа из `pDocument`.  
  
### <a name="remarks"></a>Примечания  
 `CDataRecoveryHandler` Использует имя документа в качестве ключа в `m_mapDocNameToAutosaveName`, `m_mapDocNameToDocumentPtr`, и `m_mapDocNameToRestoreBool`. Включение этих параметров `CDataRecoveryHandler` для наблюдения за `CDocument` объектов, эта функция имя файла и параметров автосохранения.  
  
##  <a name="getnormaldocumenttitle"></a>CDataRecoveryHandler::GetNormalDocumentTitle  
 Извлекает обычного заголовка в указанном документе.  
  
```  
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на `CDocument`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обычного заголовка в указанном документе.  
  
### <a name="remarks"></a>Примечания  
 Обычного заголовка документа обычно — имя файла документа без пути. Это название в **имя файла** поле **Сохранить как** диалоговое окно.  
  
##  <a name="getrecovereddocumenttitle"></a>CDataRecoveryHandler::GetRecoveredDocumentTitle  
 Создает и возвращает заголовок для восстановленного документа.  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strDocumentTitle`  
 Обычный заголовок для документа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Заголовок восстановленного документа.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию восстановленный заголовок документа является обычного заголовка с **[восстановлен]** к нему. Восстановленные заголовок отображается для пользователя при `CDataRecoveryHandler` запросов пользователя для восстановления автоматически сохраненная документов.  
  
##  <a name="getrestartidentifier"></a>CDataRecoveryHandler::GetRestartIdentifier  
 Извлекает идентификатор уникальный перезапуска приложения.  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Перезапуск уникальный идентификатор.  
  
### <a name="remarks"></a>Примечания  
 Перезапуск идентификатор является уникальным для каждого выполнения приложения.  
  
 `CDataRecoveryHandler` Хранит сведения в реестре о открытых документов. При диспетчера перезапуска завершает работу приложения и перезапускает его, предоставляет идентификатор перезапуска `CDataRecoveryHandler`. `CDataRecoveryHandler` Использует идентификатор перезапуска для получения списка ранее открытых документов. Это позволяет `CDataRecoveryHandler` попытаться найти и восстановить файлы автоматически сохраненная.  
  
##  <a name="getsavedocumentinfoonidle"></a>CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 Указывает, является ли `CDataRecoveryHandler` выполняет эта функция для текущего цикла простоя.  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает `CDataRecoveryHandler` преждевременном на текущего цикла простоя; `FALSE` указывает, это не так.  
  
##  <a name="getshutdownbyrestartmanager"></a>CDataRecoveryHandler::GetShutdownByRestartManager  
 Указывает, привело ли диспетчер перезапуска на выход из приложения.  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, что диспетчер перезапуска привело завершать работу; `FALSE` указывает, этого не произошло.  
  
##  <a name="initialize"></a>CDataRecoveryHandler::Initialize  
 Инициализирует объект `CDataRecoveryHandler`.  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если инициализация прошла успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Процесс инициализации загружает путь для хранения файлов автосохранения из реестра. Если `Initialize` методу не удается найти этот каталог или если путь является `NULL`, `Initialize` завершается неудачей и возвращает `FALSE`.  
  
 Используйте [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) изменение пути Автосохранение после инициализации приложения `CDataRecoveryHandler`.  
  
 `Initialize` Метод также запускает таймер для отслеживания при возникновении Далее эта функция. Используйте [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) Чтобы изменить интервал автоматического сохранения, после инициализации приложения `CDataRecoveryHandler`.  
  
##  <a name="queryrestoreautosaveddocuments"></a>CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 Отображает диалоговое окно для пользователя, для каждого документа, `CDataRecoveryHandler` автоматически сохраненная. Диалоговое окно определяет ли пользователю необходимо восстановить автоматически сохраненная документ.  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>Примечания  
 Если приложение имеет формат Юникода, этот метод отображает [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) для пользователя. В противном случае платформа использует [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) для запроса у пользователя.  
  
 После `QueryRestoreAutosavedDocuments` собирает все ответы от пользователя, эти сведения хранятся в переменной-члена `m_mapDocNameToRestoreBool`. Этот метод не восстанавливает автоматически сохраненная документов.  
  
##  <a name="readopendocumentlist"></a>CDataRecoveryHandler::ReadOpenDocumentList  
 Загружает список открытых документов из реестра.  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, что `ReadOpenDocumentList` загруженный сведений для документа, по крайней мере один из реестра; `FALSE` указывает загрузки данных в документе.  
  
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
|[in] `pDocument`|Указатель на документ, который нужно удалить.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `pDocument` был удален из списка; `FALSE` Если произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь закроет документ, платформа использует этот метод, чтобы удалить его из списка открытых документов.  
  
 Если `RemoveDocumentInfo` не удается найти `pDocument` в списке открытых документов, он не выполняет никаких действий и возвращает `TRUE`.  
  
 Чтобы использовать этот метод `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` должна быть задана в `m_dwRestartManagerSupportFlags`.   
  
##  <a name="reopenpreviousdocuments"></a>CDataRecoveryHandler::ReopenPreviousDocuments  
 Открывает ранее открытых документов.  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если хотя бы один документ был открыт; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод открывает последнего сохранения ранее открытых документов. Если документ не был сохранен или автоматически сохраненная, `ReopenPreviousDocuments` открывает новый документ на основе шаблона для данного типа файлов.  
  
 Чтобы использовать этот метод `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` должна быть задана в `m_dwRestartManagerSupportFlags`. Если этот параметр не задан, `ReopenPreviousDocuments` не выполняет никаких действий и возвращает `FALSE`.  
  
 Если нет документов, хранящихся в списке ранее открытых документов `ReopenPreviousDocuments` не выполняет никаких действий и возвращает `FALSE`.  
  
##  <a name="restoreautosaveddocuments"></a>CDataRecoveryHandler::RestoreAutosavedDocuments  
 Восстанавливает автоматически сохраненная документов на основе ввода пользователя.  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод восстанавливает успешно документов.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) для определения того, что документы пользователя требуется восстановить. Если пользователь решает не восстановить документ автоматически сохраненная `RestoreAutosavedDocuments` автосохранения файл удаляется. В противном случае `RestoreAutosavedDocuments` автоматически сохраненная версия заменяет открытый документ.  
  
 С помощью этого метода, либо `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` или `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES` должна быть задана в `m_dwRestartManagerSupportFlags`.   
  
##  <a name="saveopendocumentlist"></a>CDataRecoveryHandler::SaveOpenDocumentList  
 Сохраняет текущий список открытых документов в реестре Windows.  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если нет открытых документов, чтобы сохранить или если они были успешно сохранены. `FALSE`Если имеются документы, чтобы сохранить в реестре, но они не были сохранены, так как произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Диспетчер перезапуска вызовы `SaveOpenDocumentList` при завершении работы приложения неожиданно или при выходе из для обновления. При повторном запуске приложения, она использует [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) получение списка открытых документов.  
  
 Этот метод сохраняет только список открытых документов. Метод [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) отвечает за сохранение документов, сами.  
  
##  <a name="setautosaveinterval"></a>CDataRecoveryHandler::SetAutosaveInterval  
 Задает интервал между циклами автосохранения в миллисекундах.  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nAutosaveInterval`  
 Новый интервал автоматического сохранения в миллисекундах.  
  
##  <a name="setautosavepath"></a>CDataRecoveryHandler::SetAutosavePath  
 Задает каталог, в которой хранятся файлы автоматически сохраненная.  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `strAutosavePath`|Путь, где хранятся файлы автоматического сохранения.|  
  
### <a name="remarks"></a>Примечания  
 Изменение каталога автосохранения не перемещает файлы автоматически сохраненная в настоящее время.  
  
##  <a name="setrestartidentifier"></a>CDataRecoveryHandler::SetRestartIdentifier  
 Задает перезапуск уникальный идентификатор для этого экземпляра `CDataRecoveryHandler`.  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `strRestartIdentifier`|Уникальный идентификатор диспетчера перезапуска.|  
  
### <a name="remarks"></a>Примечания  
 Диспетчер перезапуска записывает сведения об открытых документов в реестре. Эти сведения сохраняются вместе с перезапуска уникальный идентификатор в виде ключа. Из-за перезапуска идентификатор является уникальным для каждого экземпляра приложения, может неожиданно прекратить работу нескольких экземпляров приложения, и диспетчер перезапуска каждой из них можно восстановить.  
  
##  <a name="setsavedocumentinfoonidle"></a>CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 Задает ли `CDataRecoveryHandler` сохраняет сведения о открытый документ в реестр Windows в течение текущего цикла простоя.  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `bSaveOnIdle`|`TRUE`Чтобы сохранить сведения о документе во время текущего цикла простоя; `FALSE to not perform a save`.|  
  
##  <a name="setshutdownbyrestartmanager"></a>CDataRecoveryHandler::SetShutdownByRestartManager  
 Задает ли предыдущих выхода приложения была вызвана диспетчера перезапуска.  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `bShutdownByRestartManager`|`TRUE`Чтобы указать, что диспетчер перезапуска привело завершать работу; `FALSE` для указания, что выхода из приложения по другой причине.|  
  
### <a name="remarks"></a>Примечания  
 Платформа ведет себя по-разному на основе предыдущих выхода непредвиденный или она была начата с диспетчера перезапуска.  
  
##  <a name="updatedocumentinfo"></a>CDataRecoveryHandler::UpdateDocumentInfo  
 Обновляет данные о документа, так как он сохраненные пользователем.  
  
```  
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDocument`|Указатель на сохраненный документ.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если этот метод удалить документ автоматически сохраненная и обновить сведения о документе; `FALSE` Если произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь сохраняет документ, приложение удаляет файл автоматически сохраненная, так как он больше не нужен. `UpdateDocumentInfo`Удаляет файл автоматически сохраненная путем вызова [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo). `UpdateDocumentInfo`Добавляет сведения из `pDocument` в список в настоящее время открытия документов, так как `RemoveDocumentInfo` удаляет эти сведения, а сохраненные по-прежнему открыт документ.  
  
 Чтобы использовать этот метод `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` должна быть задана в `m_dwRestartManagerSupportFlags`.   
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Практическое руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)


