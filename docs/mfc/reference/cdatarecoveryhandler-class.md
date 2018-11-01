---
title: Класс CDataRecoveryHandler
ms.date: 11/04/2016
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
helpviewer_keywords:
- CDataRecoveryHandler [MFC], CDataRecoveryHandler
- CDataRecoveryHandler [MFC], AutosaveAllDocumentInfo
- CDataRecoveryHandler [MFC], AutosaveDocumentInfo
- CDataRecoveryHandler [MFC], CreateDocumentInfo
- CDataRecoveryHandler [MFC], DeleteAllAutosavedFiles
- CDataRecoveryHandler [MFC], DeleteAutosavedFile
- CDataRecoveryHandler [MFC], GenerateAutosaveFileName
- CDataRecoveryHandler [MFC], GetAutosaveInterval
- CDataRecoveryHandler [MFC], GetAutosavePath
- CDataRecoveryHandler [MFC], GetDocumentListName
- CDataRecoveryHandler [MFC], GetNormalDocumentTitle
- CDataRecoveryHandler [MFC], GetRecoveredDocumentTitle
- CDataRecoveryHandler [MFC], GetRestartIdentifier
- CDataRecoveryHandler [MFC], GetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], GetShutdownByRestartManager
- CDataRecoveryHandler [MFC], Initialize
- CDataRecoveryHandler [MFC], QueryRestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], ReadOpenDocumentList
- CDataRecoveryHandler [MFC], RemoveDocumentInfo
- CDataRecoveryHandler [MFC], ReopenPreviousDocuments
- CDataRecoveryHandler [MFC], RestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], SaveOpenDocumentList
- CDataRecoveryHandler [MFC], SetAutosaveInterval
- CDataRecoveryHandler [MFC], SetAutosavePath
- CDataRecoveryHandler [MFC], SetRestartIdentifier
- CDataRecoveryHandler [MFC], SetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], SetShutdownByRestartManager
- CDataRecoveryHandler [MFC], UpdateDocumentInfo
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
ms.openlocfilehash: 10107d7b815f8a3c479a28de8ff07439b5da2fda
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456047"
---
# <a name="cdatarecoveryhandler-class"></a>Класс CDataRecoveryHandler

`CDataRecoveryHandler` Преждевременном прекращении работы, документы и восстанавливает их, если приложение неожиданно завершает работу.

## <a name="syntax"></a>Синтаксис

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|||
|-|-|
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Создает объект `CDataRecoveryHandler`.|

### <a name="methods"></a>Методы

|||
|-|-|
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|Каждый файл зарегистрирован с преждевременном прекращении работы `CDataRecoveryHandler` класса.|
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|Преждевременном прекращении работы указанного документа.|
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|Добавляет документ в список открытых документов.|
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|Удаляет все текущие файлы автоматическое сохранение.|
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|Удаляет указанный автоматическое сохранение файла.|
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|Создает имя файла автосохранения, связанный с предоставленным имени файла.|
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Возвращает интервал между попытками автосохранения.|
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Возвращает путь к файлам автоматическое сохранение.|
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Возвращает имя документа из `CDocument` объекта.|
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Извлекает заголовок обычной для указанного документа.|
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Создает и возвращает заголовок для восстановленного документа.|
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Извлекает идентификатор уникальный перезапуска приложения.|
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|Указывает, является ли `CDataRecoveryHandler` выполняет автосохранения для текущего цикла простоя.|
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Указывает, привело ли диспетчер перезапуска выхода из приложения.|
|[CDataRecoveryHandler::Initialize](#initialize)|Инициализирует объект `CDataRecoveryHandler`.|
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|Отображает диалоговое окно для пользователя, для каждого `CDataRecoveryHandler` автоматическое сохранение. Диалоговое окно определяет ли пользователь хочет восстановить автоматическое сохранение документа.|
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Загружает список открытых документов из реестра.|
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Удаляет указанный документ из список открытых документов.|
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Открывает ранее открытые документы.|
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|Восстанавливает автоматическое сохранение документов на основе ввода пользователя.|
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Сохраняет текущий список открытых документов в реестр Windows.|
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Задает время между циклами автосохранения в миллисекундах.|
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Задает каталог, где хранятся файлы автоматическое сохранение.|
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Задает перезапуска уникальный идентификатор для данного экземпляра `CDataRecoveryHandler`.|
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|Наборы ли `CDataRecoveryHandler` сохраняет сведения о открытый документ в реестр Windows во время текущего цикла простоя.|
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|Задает ли предыдущих выхода приложения было вызвано диспетчером перезапуска.|
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Обновляет сведения о для документа, так как он сохранен.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|m_bRestoringPreviousOpenDocs|Указывает, открывается ли обработчик восстановления данных ранее открытые документы.|
|m_bSaveDocumentInfoOnIdle|Указывает ли преждевременном прекращении работы обработчика для восстановления данных документов на следующий цикл простоя.|
|m_bShutdownByRestartManager|Указывает, вызывает ли диспетчер перезапуска выхода из приложения.|
|m_dwRestartManagerSupportFlags|Флаги, указывающие, что поддержка диспетчера перезапуска обеспечивает для приложения.|
|m_lstAutosavesToDelete|Список автоматическое сохранение файлов, которые не были удалены, когда исходные документы были закрыты. При выходе из приложения, повторная попытка запуска диспетчера перезапуска, при удалении файлов.|
|m_mapDocNameToAutosaveName|Сопоставление имен документа на автоматическое сохранение имена файлов.|
|m_mapDocNameToDocumentPtr|Сопоставление имен документа для [CDocument](../../mfc/reference/cdocument-class.md) указатели.|
|m_mapDocNameToRestoreBool|Сопоставление имен документа, чтобы логический параметр, который указывает, следует ли восстановить автоматическое сохранение документа.|
|m_mapDocumentPtrToDocName|Карта `CDocument` указателей на имена документов.|
|m_mapDocumentPtrToDocTitle|Карта `CDocument` указатели на заголовки документов. Эти заголовки используются для сохранения файлов.|
|m_nAutosaveInterval|Время в миллисекундах между преждевременном прекращении работы.|
|m_nTimerID|Идентификатор таймера автосохранения.|
|m_strAutosavePath|Расположение, где хранятся автоматическое сохранение документов.|
|m_strRestartIdentifier|Строковое представление идентификатора GUID диспетчера перезапуска.|

## <a name="remarks"></a>Примечания

Использует диспетчер перезапуска `CDataRecoveryHandler` класса следует отслеживать все открытые документы и сохранять их при необходимости. Чтобы включить автосохранения, используйте [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) метод. Этот метод указывает `CDataRecoveryHandler` провести автосохранения Далее цикла простоя. Вызовы диспетчера перезапуска `SetSaveDocumentInfoOnIdle` при `CDataRecoveryHandler` следует выполнять автосохранения.

Все методы `CDataRecoveryHandler` класса являются виртуальными. Переопределите методы в этот класс для создания собственного обработчика восстановления пользовательских данных. Если вы создаете собственный обработчик восстановления данных или диспетчер перезапуска, не следует создавать экземпляры CDataRecoveryHandler. [Класс CWinApp](../../mfc/reference/cwinapp-class.md) создает `CDataRecoveryHandler` объекта, так как это требуется.

Перед использованием `CDataRecoveryHandler` объекта, необходимо вызвать [CDataRecoveryHandler::Initialize](#initialize).

Так как `CDataRecoveryHandler` класс тесно подключен к диспетчера перезапуска, `CDataRecoveryHandler` зависит от глобального параметра `m_dwRestartManagerSupportFlags`. Этот параметр определяет, какие разрешения имеет диспетчер перезапуска и его взаимодействия с приложением. Чтобы включить диспетчер перезапуска в существующее приложение, необходимо назначить `m_dwRestartManagerSupportFlags` соответствующее значение в конструкторе объекта основного приложения. Дополнительные сведения об использовании диспетчера перезапуска см. в разделе [как: Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md).

## <a name="requirements"></a>Требования

**Заголовок:** afxdatarecovery.h

##  <a name="autosavealldocumentinfo"></a>  CDataRecoveryHandler::AutosaveAllDocumentInfo

Каждый файл зарегистрирован с преждевременном прекращении работы `CDataRecoveryHandler` класса.

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если `CDataRecoveryHandler` сохраненных документов; FALSE, если документ не был сохранен.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение TRUE, если нет документов, которые необходимо сохранить. Он также возвращает значение TRUE без сохранения всех документов, если извлечение `CWinApp` или `CDocManager` для приложения приводит к ошибке.

Чтобы использовать этот метод, необходимо задать AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART или AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL в `m_dwRestartManagerSupportFlags`. См. в разделе [m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) Дополнительные сведения.

##  <a name="autosavedocumentinfo"></a>  CDataRecoveryHandler::AutosaveDocumentInfo

Преждевременном прекращении работы указанного документа.

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pDocument*|[in] Указатель на `CDocument` для сохранения.|
|*bResetModifiedFlag*|[in] Значение TRUE указывает, что `CDataRecoveryHandler` рассматривает *pDocument* изменяемые; Значение FALSE указывает, что инфраструктура считает *pDocument* быть без изменений. Дополнительные сведения о влиянии этого флага в разделе "Примечания".|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если заданы соответствующие флаги и *pDocument* является допустимым `CDocument` объекта.

### <a name="remarks"></a>Примечания

Каждый `CDocument` объект имеет флаг, указывающий, если он был изменен с момента последнего сохранения. Используйте [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) для определения состояния этого флага. Если `CDocument` не изменился с момента последнего сохранения, `AutosaveDocumentInfo` удаляет все файлы автоматически сохраненная для этого документа. Если документ был изменен с момента последнего сохранения, закройте приложение предлагает пользователю сохранить документ перед закрытием.

> [!NOTE]
>  С помощью *bResetModifiedFlag* для изменения состояния документа к неизмененной чего пользователь может потерять несохраненные данные. Если платформа считает, что документ без изменений, закройте приложение не запрашивает пользователь может сохранить.

Этот метод создает исключение с [ASSERT](diagnostic-services.md#assert) макрос Если *pDocument* не является допустимым `CDocument` объекта.

Чтобы использовать этот метод, необходимо задать AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART или AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL в *m_dwRestartManagerSupportFlags*.

##  <a name="cdatarecoveryhandler"></a>  CDataRecoveryHandler::CDataRecoveryHandler

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
|*dwRestartManagerSupportFlags*|[in] Указывает, какие параметры диспетчера перезапуска, поддерживаются.|
|*nAutosaveInterval*|[in] Время между преждевременном прекращении работы. Этот параметр указывается в миллисекундах.|

### <a name="remarks"></a>Примечания

Платформа MFC автоматически создает `CDataRecoveryHandler` для приложения при использовании **новый проект** мастера. Если вы настраиваете поведение при восстановлении данных или диспетчер перезапуска, не следует создавать `CDataRecoveryHandler` объекта.

##  <a name="createdocumentinfo"></a>  CDataRecoveryHandler::CreateDocumentInfo

Добавляет документ в список открытых документов.

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pDocument*|[in] Указатель на `CDocument`. Этот метод создает сведения о документе для данного `CDocument`.|

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Этот метод проверяет, если *pDocument* уже находится в список документов, прежде чем его добавить документ. Если *pDocument* уже находится в списке, этот метод удаляет файл автоматическое сохранение, связанный с *pDocument*.

Чтобы использовать этот метод, необходимо задать AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART или AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL в *m_dwRestartManagerSupportFlags*.

##  <a name="deleteallautosavedfiles"></a>  CDataRecoveryHandler::DeleteAllAutosavedFiles

Удаляет все текущие файлы автоматическое сохранение.

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию всегда возвращает значение TRUE.

##  <a name="deleteautosavedfile"></a>  CDataRecoveryHandler::DeleteAutosavedFile

Удаляет указанный автоматическое сохранение файла.

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*strAutosavedFile*|[in] Строка, содержащая имя файла автоматическое сохранение.|

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Если этот метод не может удалить файл автоматическое сохранение, она сохраняет имя файла в список. Деструктор для `CDataRecoveryHandler` делается попытка удалить каждый автоматическое сохранение файла, указанного в этом списке.

##  <a name="generateautosavefilename"></a>  CDataRecoveryHandler::GenerateAutosaveFileName

Создает имя файла автосохранения, связанный с предоставленным имени файла.

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>Параметры

*strDocumentName*<br/>
[in] Строка, содержащая имя документа. `GenerateAutosaveFileName` использует это имя документа, для создания соответствующее имя файла автосохранения.

### <a name="return-value"></a>Возвращаемое значение

Имя файла автосохранения, созданный из *strDocumentName*.

### <a name="remarks"></a>Примечания

Каждое имя документа имеет взаимно-однозначное сопоставление с именем файла автосохранения.

##  <a name="getautosaveinterval"></a>  CDataRecoveryHandler::GetAutosaveInterval

Возвращает интервал между попытками автосохранения.

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>Возвращаемое значение

Время в миллисекундах между автосохранения пытается подключиться.

##  <a name="getautosavepath"></a>  CDataRecoveryHandler::GetAutosavePath

Возвращает путь к файлам автоматическое сохранение.

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Расположение, где хранятся автоматическое сохранение документов.

##  <a name="getdocumentlistname"></a>  CDataRecoveryHandler::GetDocumentListName

Возвращает имя документа из `CDocument` объекта.

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pDocument*|[in] Указатель на `CDocument`. `GetDocumentListName` Возвращает имя документа из этого `CDocument`.|

### <a name="return-value"></a>Возвращаемое значение

Имя документа из *pDocument*.

### <a name="remarks"></a>Примечания

`CDataRecoveryHandler` Использует имя документа в качестве ключа в *m_mapDocNameToAutosaveName*, *m_mapDocNameToDocumentPtr*, и *m_mapDocNameToRestoreBool*. Включение этих параметров `CDataRecoveryHandler` для наблюдения за `CDocument` объекты, имя файла автосохранения и параметров автосохранения.

##  <a name="getnormaldocumenttitle"></a>  CDataRecoveryHandler::GetNormalDocumentTitle

Извлекает заголовок обычной для указанного документа.

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pDocument*|[in] Указатель на `CDocument`.|

### <a name="return-value"></a>Возвращаемое значение

Обычный заголовок в указанном документе.

### <a name="remarks"></a>Примечания

Обычный заголовок документа обычно — имя файла документа без пути. Это заголовок в **имя файла** поле **Сохранить как** диалоговое окно.

##  <a name="getrecovereddocumenttitle"></a>  CDataRecoveryHandler::GetRecoveredDocumentTitle

Создает и возвращает заголовок для восстановленного документа.

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>Параметры

*strDocumentTitle*<br/>
[in] Обычный заголовок для документа.

### <a name="return-value"></a>Возвращаемое значение

Заголовок восстановленного документа.

### <a name="remarks"></a>Примечания

По умолчанию, восстановленные заголовок документа — обычный название с указанием **[Восстановленный]** добавленным к нему. Восстановленные заголовок отображается для пользователя при `CDataRecoveryHandler` запрашивает пользователя, чтобы восстановить автоматическое сохранение документов.

##  <a name="getrestartidentifier"></a>  CDataRecoveryHandler::GetRestartIdentifier

Извлекает идентификатор уникальный перезапуска приложения.

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>Возвращаемое значение

Перезапуск уникальный идентификатор.

### <a name="remarks"></a>Примечания

Перезапуск идентификатор уникален для каждого выполнения приложения.

`CDataRecoveryHandler` Хранит сведения в реестре о открытых документах. Когда диспетчер перезапуска завершает работу приложения и перезапускает его, он передает идентификатор перезапуска `CDataRecoveryHandler`. `CDataRecoveryHandler` Использует идентификатор перезапуска, чтобы получить список ранее открытые документы. Это позволяет `CDataRecoveryHandler` попытаться найти и восстановить автоматическое сохранение файлов.

##  <a name="getsavedocumentinfoonidle"></a>  CDataRecoveryHandler::GetSaveDocumentInfoOnIdle

Указывает, является ли `CDataRecoveryHandler` выполняет автосохранения для текущего цикла простоя.

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает `CDataRecoveryHandler` преждевременном прекращении работы на текущего цикла простоя; Значение FALSE указывает, что это не так.

##  <a name="getshutdownbyrestartmanager"></a>  CDataRecoveryHandler::GetShutdownByRestartManager

Указывает, привело ли диспетчер перезапуска выхода из приложения.

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска привело завершать работу; Значение FALSE указывает, что этого не произошло.

##  <a name="initialize"></a>  CDataRecoveryHandler::Initialize

Инициализирует объект `CDataRecoveryHandler`.

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если инициализация прошла успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Процесс инициализации загружает путь для хранения файлов автосохранения из реестра. Если `Initialize` методу не удается найти этот каталог, или если путь имеет значение NULL, `Initialize` завершается неудачей и возвращает `FALSE`.

Используйте [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) Чтобы изменить путь автосохранения после инициализации приложения `CDataRecoveryHandler`.

`Initialize` Метод также запускает таймер для отслеживания при возникновении автосохранения Далее. Используйте [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) этот интервал автосохранения после инициализации приложения `CDataRecoveryHandler`.

##  <a name="queryrestoreautosaveddocuments"></a>  CDataRecoveryHandler::QueryRestoreAutosavedDocuments

Отображает диалоговое окно для пользователя, для каждого `CDataRecoveryHandler` автоматическое сохранение. Диалоговое окно определяет ли пользователь хочет восстановить автоматическое сохранение документа.

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>Примечания

Если приложение используется Юникод, этот метод отображает [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) для пользователя. В противном случае платформа использует [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) , чтобы запросить пользователя.

После `QueryRestoreAutosavedDocuments` собирает все ответы от пользователя, эти сведения хранятся в переменной-члена *m_mapDocNameToRestoreBool*. Этот метод не восстанавливает автоматическое сохранение документов.

##  <a name="readopendocumentlist"></a>  CDataRecoveryHandler::ReadOpenDocumentList

Загружает список открытых документов из реестра.

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что `ReadOpenDocumentList` загрузить данные для по крайней мере один документ из реестра; Значение FALSE указывает, что был загружен нет сведений о документе.

### <a name="remarks"></a>Примечания

Эта функция загружает открытый документ сведения из реестра и сохраняет его в переменной-члена *m_mapDocNameToAutosaveName*.

После `ReadOpenDocumentList` загружает все данные, она удаляет данные документа из реестра.

##  <a name="removedocumentinfo"></a>  CDataRecoveryHandler::RemoveDocumentInfo

Удаляет указанный документ из список открытых документов.

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pDocument*|[in] Указатель на документ, который необходимо удалить.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *pDocument* был удален из списка; Значение FALSE, если произошла ошибка.

### <a name="remarks"></a>Примечания

Когда пользователь закрывает документ, инфраструктура использует этот метод, чтобы удалить его из списка открытых документов.

Если `RemoveDocumentInfo` не удается найти *pDocument* в список открытых документов, он не выполняет никаких действий и возвращает значение TRUE.

Чтобы использовать этот метод, необходимо задать AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES в *m_dwRestartManagerSupportFlags*.

##  <a name="reopenpreviousdocuments"></a>  CDataRecoveryHandler::ReopenPreviousDocuments

Открывает ранее открытые документы.

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если хотя бы один документ был открыт; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод открывает последнего сохранения ранее открытые документы. Если документ не был сохранен или автоматическое сохранение, `ReopenPreviousDocuments` откроется пустой документ на основе шаблона для этого типа файлов.

Чтобы использовать этот метод, необходимо задать AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES в *m_dwRestartManagerSupportFlags*. Если этот параметр не задан, `ReopenPreviousDocuments` ничего не делает и возвращает значение FALSE.

Если нет документов, хранящихся в списке ранее открытые документы `ReopenPreviousDocuments` ничего не делает и возвращает значение FALSE.

##  <a name="restoreautosaveddocuments"></a>  CDataRecoveryHandler::RestoreAutosavedDocuments

Восстанавливает автоматическое сохранение документов на основе ввода пользователя.

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод успешно восстанавливает документы.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) для определения, который Документирует пользователь хочет восстановить. Если пользователь решает не восстановить документ автоматически сохраненная `RestoreAutosavedDocuments` удаляет файл автосохранения. В противном случае `RestoreAutosavedDocuments` автоматически сохраненная версия заменяет открытый документ.

Чтобы использовать этот метод, необходимо задать AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES или AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES в `m_dwRestartManagerSupportFlags`.

##  <a name="saveopendocumentlist"></a>  CDataRecoveryHandler::SaveOpenDocumentList

Сохраняет текущий список открытых документов в реестр Windows.

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если нет открытых документов, чтобы сохранить или если они были успешно сохранены. Значение FALSE, если имеются документы, чтобы сохранить в реестре, но они не были сохранены, так как произошла ошибка.

### <a name="remarks"></a>Примечания

Вызовы диспетчера перезапуска `SaveOpenDocumentList` при выходе из приложения неожиданно или завершении обновления. При повторном запуске приложения, он использует [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) для получения списка открытых документов.

Этот метод сохраняет список открытых документов. Метод [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) отвечает за сохранение самих документах.

##  <a name="setautosaveinterval"></a>  CDataRecoveryHandler::SetAutosaveInterval

Задает время между циклами автосохранения в миллисекундах.

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>Параметры

*nAutosaveInterval*<br/>
[in] Новый автосохранения интервал в миллисекундах.

##  <a name="setautosavepath"></a>  CDataRecoveryHandler::SetAutosavePath

Задает каталог, где хранятся файлы автоматическое сохранение.

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*strAutosavePath*|[in] Путь, где хранятся файлы автосохранения.|

### <a name="remarks"></a>Примечания

Изменение каталога автосохранения не перемещаются в настоящее время автоматическое сохранение файлов.

##  <a name="setrestartidentifier"></a>  CDataRecoveryHandler::SetRestartIdentifier

Задает перезапуска уникальный идентификатор для данного экземпляра `CDataRecoveryHandler`.

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*strRestartIdentifier*|[in] Уникальный идентификатор диспетчера перезапуска.|

### <a name="remarks"></a>Примечания

Диспетчер перезапуска записывает сведения об открытых документов в реестре. Эти сведения сохраняются вместе с перезапуска уникальный идентификатор в виде ключа. Так как перезапуск идентификатор является уникальным для каждого экземпляра приложения, может неожиданно завершить работу нескольких экземпляров приложения и диспетчером перезапуска можно восстановить каждый из них.

##  <a name="setsavedocumentinfoonidle"></a>  CDataRecoveryHandler::SetSaveDocumentInfoOnIdle

Наборы ли `CDataRecoveryHandler` сохраняет сведения о открытый документ в реестр Windows во время текущего цикла простоя.

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*bSaveOnIdle*|[in] Значение TRUE, чтобы сохранить сведения о документе в течение текущего цикла простоя; Значение FALSE, если не выполнить сохранение.|

##  <a name="setshutdownbyrestartmanager"></a>  CDataRecoveryHandler::SetShutdownByRestartManager

Задает ли предыдущих выхода приложения было вызвано диспетчером перезапуска.

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*bShutdownByRestartManager*|[in] Значение TRUE указывает, что диспетчер перезапуска привело завершать работу; Значение FALSE указывает, что приложение завершило работу по другой причине.|

### <a name="remarks"></a>Примечания

Платформа ведет себя по-разному на основе предыдущих exit непредвиденное или она была начата с диспетчером перезапуска.

##  <a name="updatedocumentinfo"></a>  CDataRecoveryHandler::UpdateDocumentInfo

Обновляет сведения о для документа, так как он сохранен.

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pDocument*|[in] Указатель на сохраненный документ.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод, удалить его автоматическое сохранение и обновить сведения о документе; Значение FALSE, если произошла ошибка.

### <a name="remarks"></a>Примечания

Когда пользователь сохраняет документ, приложение удаляет автоматическое сохранение файла, так как он больше не требуется. `UpdateDocumentInfo` Удаляет файл автоматическое сохранение, вызвав [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo). `UpdateDocumentInfo` добавляет информацию из *pDocument* в список в настоящее время открытия документов, так как `RemoveDocumentInfo` удаляет эту информацию, но сохраненные по-прежнему открыт документ.

Чтобы использовать этот метод, необходимо задать AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES в *m_dwRestartManagerSupportFlags*.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Практическое руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)

