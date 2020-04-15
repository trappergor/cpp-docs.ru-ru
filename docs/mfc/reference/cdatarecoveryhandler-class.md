---
title: Класс CDataRecoveryHandler
ms.date: 03/27/2019
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
ms.openlocfilehash: bdfcbea6c345235358384691388afcdbbd2d0a42
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321934"
---
# <a name="cdatarecoveryhandler-class"></a>Класс CDataRecoveryHandler

Автосохраняет `CDataRecoveryHandler` документы и восстанавливает их, если приложение неожиданно выходит.

## <a name="syntax"></a>Синтаксис

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|||
|-|-|
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|Формирует объект `CDataRecoveryHandler`.|

### <a name="methods"></a>Методы

|||
|-|-|
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|Автосохраняет каждый файл, `CDataRecoveryHandler` зарегистрированный в классе.|
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|Автосохраняет указанный документ.|
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|Добавляет документ в список открытых документов.|
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|Удаляет все текущие файлы автосохраненных.|
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|Удаляет указанный файл автосохраненных.|
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|Генерирует имя файла автосохранения, связанного с именем файла документа.|
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|Возвращает интервал между попытками автосохранения.|
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|Возвращает путь автосохраненных файлов.|
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|Извлекает имя документа `CDocument` из объекта.|
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|Извлекает обычное название для указанного документа.|
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|Создает и возвращает заголовок для восстановленного документа.|
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|Извлекает уникальный идентификатор перезагрузки для приложения.|
|[CDataRecoveryHandler::GetSaveDocumentInfoonidle](#getsavedocumentinfoonidle)|Указывает, `CDataRecoveryHandler` выполняет ли автосохранение на текущем цикле простоя.|
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|Указывает, вызвал ли менеджер перезагрузки приложение к выходу.|
|[CDataRecoveryHandler::Первоначальнизировать](#initialize)|Инициализирует объект `CDataRecoveryHandler`.|
|[CDataRecoveryHandler::КвиреставрацияАвтосаведокументы](#queryrestoreautosaveddocuments)|Отображает для пользователя диалоговое окно для каждого `CDataRecoveryHandler` документа, который автоматически сохраняется. Коробка диалогов определяет, хочет ли пользователь восстановить автоматически сохраненный документ.|
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|Загружает открытый список документов из реестра.|
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|Удаляет предоставленный документ из списка открытых документов.|
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|Открывает ранее открытые документы.|
|[CDataRecoveryHandler::RestoreAutosavedДокументы](#restoreautosaveddocuments)|Восстанавливает автоматически сохраненные документы на основе пользовательского ввода.|
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|Сохраняет текущий список открытых документов в реестре Windows.|
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|Устанавливает время между циклами автосохранения в миллисекундах.|
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|Устанавливает каталог, в котором хранятся автоматически сохраненные файлы.|
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|Устанавливает уникальный идентификатор перезагрузки для данного экземпляра. `CDataRecoveryHandler`|
|[CDataRecoveryHandler::SetSaveDocumentinfoonidle](#setsavedocumentinfoonidle)|Устанавливает, `CDataRecoveryHandler` сохраняет ли информация об открытых документах в реестре Windows в течение текущего цикла простоя.|
|[CDataRecoveryHandler::SetShutdownbyRestartManager](#setshutdownbyrestartmanager)|Устанавливает, был ли предыдущий выход приложения вызван менеджером перезагрузки.|
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|Обновляет информацию для документа, потому что пользователь сохранил его.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|m_bRestoringPreviousOpenDocs|Указывает, открывает ли обработчик восстановления данных ранее открытые документы.|
|m_bSaveDocumentInfoOnIdle|Указывает, автоматически ли обработка восстановления данных сохраняет документы на следующем цикле простоя.|
|m_bShutdownByRestartManager|Указывает, вызывает ли менеджер перезагрузки приложение к выходу.|
|m_dwRestartManagerSupportFlags|Флаги, указывающие, какую поддержку обеспечивает менеджер перезагрузки для приложения.|
|m_lstAutosavesToDelete|Список автоматически сохраненных файлов, которые не были удалены при закрытии исходных документов. Когда приложение выходит из него, менеджер перезагрузки повторно удаляет файлы.|
|m_mapDocNameToAutosaveName|Карта имен документов для автоматически сохраненных имен файлов.|
|m_mapDocNameToDocumentPtr|Карта имен документов в указателях [CDocument.](../../mfc/reference/cdocument-class.md)|
|m_mapDocNameToRestoreBool|Карта документа называется параметром Boolean, который указывает, следует ли восстановить документ автосохраненных.|
|m_mapDocumentPtrToDocName|Карта указателей `CDocument` на имена документов.|
|m_mapDocumentPtrToDocTitle|Карта указателей `CDocument` на заголовки документов. Эти названия используются для сохранения файлов.|
|m_nAutosaveInterval|Время в миллисекундах между автосасивами.|
|m_nTimerID|Идентификатор для таймер автосохранения.|
|m_strAutosavePath|Место, где хранятся автоматически сохраненные документы.|
|m_strRestartIdentifier|Строка представления GUID для менеджера перезагрузки.|

## <a name="remarks"></a>Remarks

Менеджер перезагрузки `CDataRecoveryHandler` использует класс для отслеживания всех открытых документов и автоматического их сохранения по мере необходимости. Для автоматического сохранения используйте метод [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.](#setsavedocumentinfoonidle) Этот метод направляет `CDataRecoveryHandler` для выполнения автосохранения на следующем цикле простоя. Менеджер перезагрузки `SetSaveDocumentInfoOnIdle` вызывает, `CDataRecoveryHandler` когда должен выполнить автосохранение.

Все методы `CDataRecoveryHandler` класса являются виртуальными. Переопределить методы в этом классе, чтобы создать свой собственный пользовательский обработчик восстановления данных. Если вы не создадите свой собственный обработчик восстановления данных или не перезапустите менеджер, не мгновите CDataRecoveryHandler. [Класс CWinApp](../../mfc/reference/cwinapp-class.md) создает `CDataRecoveryHandler` объект по мере необходимости.

Прежде чем использовать `CDataRecoveryHandler` объект, необходимо позвонить [в CDataRecoveryHandler::Initialize](#initialize).

Поскольку `CDataRecoveryHandler` класс тесно связан с менеджером `CDataRecoveryHandler` перезагрузки, `m_dwRestartManagerSupportFlags`зависит от глобального параметра. Этот параметр определяет, какие разрешения есть у менеджера перезагрузки и как он взаимодействует с вашим приложением. Чтобы включить менеджер перезагрузки в существующее приложение, `m_dwRestartManagerSupportFlags` необходимо назначить соответствующее значение в конструкторе основного приложения. Для получения дополнительной информации о том, как использовать менеджер перезагрузки, [см.](../../mfc/how-to-add-restart-manager-support.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdatarecovery.h

## <a name="cdatarecoveryhandlerautosavealldocumentinfo"></a><a name="autosavealldocumentinfo"></a>CDataRecoveryHandler::AutosaveAllDocumentInfo

Автосохраняет каждый файл, `CDataRecoveryHandler` зарегистрированный в классе.

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, `CDataRecoveryHandler` если сохранены все документы; FALSE, если какой-либо документ не был сохранен.

### <a name="remarks"></a>Remarks

Этот метод возвращает TRUE, если нет документов, которые должны быть сохранены. Он также возвращает TRUE без сохранения `CWinApp` `CDocManager` каких-либо документов, если получение или для приложения генерирует ошибку.

Чтобы использовать этот метод, необходимо установить `m_dwRestartManagerSupportFlags`AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART или AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL. Для получения дополнительной информации [см.](../../mfc/how-to-add-restart-manager-support.md)

## <a name="cdatarecoveryhandlerautosavedocumentinfo"></a><a name="autosavedocumentinfo"></a>CDataRecoveryHandler::AutosaveDocumentInfo

Автосохраняет указанный документ.

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pДокумент*|(в) Указатель на `CDocument` сохранение.|
|*bResetModifiedFlag*|(в) TRUE указывает `CDataRecoveryHandler` на то, что *считается pDocument,* чтобы быть измененным; FALSE указывает на то, что платформа считает *pDocument* неизмененным. Более подробную информацию о влиянии этого флага можно просмотреть раздел «Замечания».|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если соответствующие флаги установлены `CDocument` и *pDocument* является действительным объектом.

### <a name="remarks"></a>Remarks

Каждый `CDocument` объект имеет флаг, указывающий, изменился ли он с момента последнего сохранения. Используйте [CDocument:: Изменено](../../mfc/reference/cdocument-class.md#ismodified) для определения состояния этого флага. Если `CDocument` с момента последнего сохранения не изменилось, `AutosaveDocumentInfo` удалили для этого документа любые автоматически сохраненные файлы. Если документ изменился с момента последнего сохранения, закрытие побуждает пользователя сохранить документ перед закрытием.

> [!NOTE]
> Использование *bResetModifiedFlag* для изменения состояния документа на неизмененное может привести к потере пользователем несохраненных данных. Если фреймворк считает документ неизмененным, его закрытие не подсказывает пользователю на сохранение.

Этот метод выбрасывает исключение с макросом [ASSERT,](diagnostic-services.md#assert) если *pDocument* не является действительным `CDocument` объектом.

Чтобы использовать этот метод, необходимо установить AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART или AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL в *m_dwRestartManagerSupportFlags.*

## <a name="cdatarecoveryhandlercdatarecoveryhandler"></a><a name="cdatarecoveryhandler"></a>CDataRecoveryHandler::CDataRecoveryHandler

Формирует объект `CDataRecoveryHandler`.

```
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,
    int nAutosaveInterval);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*dwRestartManagerSupportFlags*|(в) Указывает, какие параметры поддержки поддерживаются менеджером перезагрузки.|
|*nAutosaveInterval*|(в) Время между автосавами. Этот параметр находится в миллисекундах.|

### <a name="remarks"></a>Remarks

Платформа MFC автоматически `CDataRecoveryHandler` создает объект для приложения при использовании мастера **нового проекта.** Если вы настраиваете поведение восстановления данных или менеджер `CDataRecoveryHandler` перезагрузки, не следует создавать объект.

## <a name="cdatarecoveryhandlercreatedocumentinfo"></a><a name="createdocumentinfo"></a>CDataRecoveryHandler::CreateDocumentInfo

Добавляет документ в список открытых документов.

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pДокумент*|(в) Указатель на `CDocument`. Этот метод создает информацию `CDocument`о документе для этого.|

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает TRUE.

### <a name="remarks"></a>Remarks

Этот метод проверяет, если *pDocument* уже находится в списке документов, прежде чем он добавляет документ. Если *pDocument* уже в списке, этот метод удаляет автоматически сохраненный файл, связанный с *pDocument*.

Чтобы использовать этот метод, необходимо установить AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART или AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL в *m_dwRestartManagerSupportFlags.*

## <a name="cdatarecoveryhandlerdeleteallautosavedfiles"></a><a name="deleteallautosavedfiles"></a>CDataRecoveryHandler::DeleteAllAutosavedFiles

Удаляет все текущие файлы автосохраненных.

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию всегда возвращает TRUE.

## <a name="cdatarecoveryhandlerdeleteautosavedfile"></a><a name="deleteautosavedfile"></a>CDataRecoveryHandler::DeleteAutosavedFile

Удаляет указанный файл автосохраненных.

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*strAutosavedFile*|(в) Строка, содержащая имя файла autosaved.|

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию всегда возвращает TRUE.

### <a name="remarks"></a>Remarks

Если этот метод не может удалить автоматически сохраненный файл, он сохраняет имя файла в списке. Деструктор для `CDataRecoveryHandler` попыток удалить каждый автосохраненный файл, указанный в этом списке.

## <a name="cdatarecoveryhandlergenerateautosavefilename"></a><a name="generateautosavefilename"></a>CDataRecoveryHandler::GenerateAutosaveFileName

Генерирует имя файла автосохранения, связанного с именем файла документа.

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>Параметры

*strDocumentName*<br/>
(в) Строка, содержащая имя документа. `GenerateAutosaveFileName`использует это имя документа для создания соответствующего имени файла автосохранения.

### <a name="return-value"></a>Возвращаемое значение

Имя файла autosave, генерируемое на *strDocumentName*.

### <a name="remarks"></a>Remarks

Каждое имя документа имеет отображение один к одному с именем файла автосохранения.

## <a name="cdatarecoveryhandlergetautosaveinterval"></a><a name="getautosaveinterval"></a>CDataRecoveryHandler::GetAutosaveInterval

Возвращает интервал между попытками автосохранения.

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество миллисекунд между попытками автосохранения.

## <a name="cdatarecoveryhandlergetautosavepath"></a><a name="getautosavepath"></a>CDataRecoveryHandler::GetAutosavePath

Возвращает путь автосохраненных файлов.

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Место, где хранятся автоматически сохраненные документы.

## <a name="cdatarecoveryhandlergetdocumentlistname"></a><a name="getdocumentlistname"></a>CDataRecoveryHandler::GetDocumentListName

Извлекает имя документа `CDocument` из объекта.

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pДокумент*|(в) Указатель на `CDocument`. `GetDocumentListName`извлекает название документа `CDocument`из этого .|

### <a name="return-value"></a>Возвращаемое значение

Название документа от *pDocument*.

### <a name="remarks"></a>Remarks

В `CDataRecoveryHandler` качестве ключа в *m_mapDocNameToAutosaveName,* *m_mapDocNameToDocumentPtr*и *m_mapDocNameToRestoreBool*используется название документа. Эти параметры `CDataRecoveryHandler` позволяют `CDocument` отслеживать объекты, автоматическое сохранение имени файла и настройки автоматического сохранения.

## <a name="cdatarecoveryhandlergetnormaldocumenttitle"></a><a name="getnormaldocumenttitle"></a>CDataRecoveryHandler::GetNormalDocumentTitle

Извлекает обычное название для указанного документа.

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pДокумент*|(в) Указатель на `CDocument`.|

### <a name="return-value"></a>Возвращаемое значение

Обычное название для указанного документа.

### <a name="remarks"></a>Remarks

Обычное название документа обычно является названием файла документа без пути. Это название в поле **имени файла** в диалоговом поле **Save As.**

## <a name="cdatarecoveryhandlergetrecovereddocumenttitle"></a><a name="getrecovereddocumenttitle"></a>CDataRecoveryHandler::GetRecoveredDocumentTitle

Создает и возвращает заголовок для восстановленного документа.

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>Параметры

*strDocumentTitle*<br/>
(в) Обычное название документа.

### <a name="return-value"></a>Возвращаемое значение

Восстановленное название документа.

### <a name="remarks"></a>Remarks

По умолчанию восстановленное название документа является нормальным заголовком с приложеным к нему **«восстановленным».** Восстановленное название отображается пользователю, `CDataRecoveryHandler` когда пользователь запрашивает автоматически сохраненные документы.

## <a name="cdatarecoveryhandlergetrestartidentifier"></a><a name="getrestartidentifier"></a>CDataRecoveryHandler::GetRestartIdentifier

Извлекает уникальный идентификатор перезагрузки для приложения.

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор перезагрузки.

### <a name="remarks"></a>Remarks

Идентификатор перезагрузки уникален для каждого выполнения приложения.

Хранит `CDataRecoveryHandler` информацию в реестре об открытых в настоящее время документах. Когда менеджер перезагрузки выходит из приложения и перезапускает его, он `CDataRecoveryHandler`поставляет идентификатор перезагрузки в . Для `CDataRecoveryHandler` получения списка ранее открытых документов используется идентификатор перезагрузки. Это позволяет `CDataRecoveryHandler` попытаться найти и восстановить автосохраненные файлы.

## <a name="cdatarecoveryhandlergetsavedocumentinfoonidle"></a><a name="getsavedocumentinfoonidle"></a>CDataRecoveryHandler::GetSaveDocumentInfoonidle

Указывает, `CDataRecoveryHandler` выполняет ли автосохранение на текущем цикле простоя.

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает `CDataRecoveryHandler` на автосавы на текущем цикле простоя; FALSE указывает, что это не так.

## <a name="cdatarecoveryhandlergetshutdownbyrestartmanager"></a><a name="getshutdownbyrestartmanager"></a>CDataRecoveryHandler::GetShutdownByRestartManager

Указывает, вызвал ли менеджер перезагрузки приложение к выходу.

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает на то, что менеджер перезагрузки вызвал выход приложения; FALSE указывает, что это не так.

## <a name="cdatarecoveryhandlerinitialize"></a><a name="initialize"></a>CDataRecoveryHandler::Первоначальнизировать

Инициализирует объект `CDataRecoveryHandler`.

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если инициализация успешна; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Процесс инициализации загружает путь для хранения файлов автосохранения из реестра. Если `Initialize` метод не может найти этот каталог или `Initialize` если `FALSE`путь NULL, не удается и возвращается .

Используйте [CDataRecoveryHandler::SetAutosavePath,](#setautosavepath) чтобы изменить путь автосохранения `CDataRecoveryHandler`после того, как приложение инициализирует .

Метод `Initialize` также запускает таймер для мониторинга, когда происходит следующее автосохранение. Используйте [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) для изменения интервала автоматического `CDataRecoveryHandler`сохранения после того, как приложение инициализирует .

## <a name="cdatarecoveryhandlerqueryrestoreautosaveddocuments"></a><a name="queryrestoreautosaveddocuments"></a>CDataRecoveryHandler::КвиреставрацияАвтосаведокументы

Отображает для пользователя диалоговое окно для каждого `CDataRecoveryHandler` документа, который автоматически сохраняется. Коробка диалогов определяет, хочет ли пользователь восстановить автоматически сохраненный документ.

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>Remarks

Если приложение является Unicode, этот метод отображает [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) для пользователя. В противном случае платформа использует [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) для запроса пользователя.

После `QueryRestoreAutosavedDocuments` сбора всех ответов от пользователя, он хранит информацию в переменной члена *m_mapDocNameToRestoreBool*. Этот метод не восстанавливает автоматически сохраненные документы.

## <a name="cdatarecoveryhandlerreadopendocumentlist"></a><a name="readopendocumentlist"></a>CDataRecoveryHandler::ReadOpenDocumentList

Загружает открытый список документов из реестра.

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает, что `ReadOpenDocumentList` загрузил информацию по крайней мере по одному документу из реестра; FALSE указывает на отсутствие информации о документе.

### <a name="remarks"></a>Remarks

Эта функция загружает информацию об открытом документе из реестра и хранит ее в *переменной*m_mapDocNameToAutosaveName.

После `ReadOpenDocumentList` загрузки всех данных, он удаляет информацию о документе из реестра.

## <a name="cdatarecoveryhandlerremovedocumentinfo"></a><a name="removedocumentinfo"></a>CDataRecoveryHandler::RemoveDocumentInfo

Удаляет предоставленный документ из списка открытых документов.

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pДокумент*|(в) Указатель на документ для удаления.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если *pDocument* был удален из списка; FALSE, если произошла ошибка.

### <a name="remarks"></a>Remarks

Когда пользователь закрывает документ, фреймворк использует этот метод для удаления из списка открытых документов.

Если `RemoveDocumentInfo` не удается найти *pDocument* в списке открытых документов, он ничего не делает и возвращает TRUE.

Чтобы использовать этот метод, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES должны быть установлены в *m_dwRestartManagerSupportFlags.*

## <a name="cdatarecoveryhandlerreopenpreviousdocuments"></a><a name="reopenpreviousdocuments"></a>CDataRecoveryHandler::ReopenPreviousDocuments

Открывает ранее открытые документы.

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если хотя бы один документ был открыт; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Этот метод открывает последнее сохранение ранее открытых документов. Если документ не был сохранен `ReopenPreviousDocuments` или автоматически сохранен, открываетпустой документ на основе шаблона для этого типа файла.

Чтобы использовать этот метод, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES должны быть установлены в *m_dwRestartManagerSupportFlags.* Если этот параметр `ReopenPreviousDocuments` не установлен, ничего не делает и возвращает FALSE.

Если в списке ранее открытых документов `ReopenPreviousDocuments` нет документов, ничего не делает и возвращает FALSE.

## <a name="cdatarecoveryhandlerrestoreautosaveddocuments"></a><a name="restoreautosaveddocuments"></a>CDataRecoveryHandler::RestoreAutosavedДокументы

Восстанавливает автоматически сохраненные документы на основе пользовательского ввода.

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод успешно восстанавливает документы.

### <a name="remarks"></a>Remarks

Этот метод вызывает [CDataRecoveryHandler::QueryRestoreAutosavedDocuments,](#queryrestoreautosaveddocuments) чтобы определить, какие документы пользователь хочет восстановить. Если пользователь решает не восстанавливать автоматически сохраненный документ, `RestoreAutosavedDocuments` удаляет файл автосохранения. В `RestoreAutosavedDocuments` противном случае заменяет открытый документ на версию autosaved.

Чтобы использовать этот метод, необходимо установить `m_dwRestartManagerSupportFlags`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES или AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.

## <a name="cdatarecoveryhandlersaveopendocumentlist"></a><a name="saveopendocumentlist"></a>CDataRecoveryHandler::SaveOpenDocumentList

Сохраняет текущий список открытых документов в реестре Windows.

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если нет открытых документов для сохранения или если они были сохранены успешно. FALSE, если есть документы для сохранения в реестре, но они не были сохранены, потому что произошла ошибка.

### <a name="remarks"></a>Remarks

Менеджер перезагрузки `SaveOpenDocumentList` вызывает, когда приложение выходит неожиданно или когда оно выходит для обновления. Когда приложение перезапускается, оно использует [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) для получения списка открытых документов.

Этот метод сохраняет только список открытых документов. Метод [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) отвечает за сохранение самих документов.

## <a name="cdatarecoveryhandlersetautosaveinterval"></a><a name="setautosaveinterval"></a>CDataRecoveryHandler::SetAutosaveInterval

Устанавливает время между циклами автосохранения в миллисекундах.

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>Параметры

*nAutosaveInterval*<br/>
(в) Новый интервал автосохранения в миллисекундах.

## <a name="cdatarecoveryhandlersetautosavepath"></a><a name="setautosavepath"></a>CDataRecoveryHandler::SetAutosavePath

Устанавливает каталог, в котором хранятся автоматически сохраненные файлы.

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*strAutosavePath*|(в) Путь, по которому хранятся файлы автоматического сохранения.|

### <a name="remarks"></a>Remarks

Изменение каталога автосохранения не перемещает в настоящее время автоматически сохраненные файлы.

## <a name="cdatarecoveryhandlersetrestartidentifier"></a><a name="setrestartidentifier"></a>CDataRecoveryHandler::SetRestartIdentifier

Устанавливает уникальный идентификатор перезагрузки для данного экземпляра. `CDataRecoveryHandler`

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*strRestartИтификер*|(в) Уникальный идентификатор для менеджера перезагрузки.|

### <a name="remarks"></a>Remarks

Менеджер перезагрузки записывает информацию об открытых документах в реестре. Эта информация хранится с уникальным идентификатором перезагрузки в качестве ключа. Поскольку идентификатор перезагрузки уникален для каждого экземпляра приложения, несколько экземпляров приложения могут неожиданно выйти из него, и менеджер перезагрузки может восстановить каждый из них.

## <a name="cdatarecoveryhandlersetsavedocumentinfoonidle"></a><a name="setsavedocumentinfoonidle"></a>CDataRecoveryHandler::SetSaveDocumentinfoonidle

Устанавливает, `CDataRecoveryHandler` сохраняет ли информация об открытых документах в реестре Windows в течение текущего цикла простоя.

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*bSaveOnIdle*|(в) TRUE для сохранения документов в течение текущего цикла простоя; FALSE, чтобы не выполнить сохранить.|

## <a name="cdatarecoveryhandlersetshutdownbyrestartmanager"></a><a name="setshutdownbyrestartmanager"></a>CDataRecoveryHandler::SetShutdownbyRestartManager

Устанавливает, был ли предыдущий выход приложения вызван менеджером перезагрузки.

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*bShutdownByRestartManager*|(в) TRUE, чтобы указать, что менеджер перезагрузки вызвал овыходе приложения; FALSE указать, что приложение вышло по другой причине.|

### <a name="remarks"></a>Remarks

Платформа ведет себя по-разному в зависимости от того, был ли предыдущий выход неожиданным или же он был инициирован менеджером перезагрузки.

## <a name="cdatarecoveryhandlerupdatedocumentinfo"></a><a name="updatedocumentinfo"></a>CDataRecoveryHandler::UpdateDocumentInfo

Обновляет информацию для документа, потому что пользователь сохранил его.

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pДокумент*|(в) Указатель на сохраненный документ.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если этот метод удалил документ автосохраненных и обновил информацию о документе; FALSE, если произошла ошибка.

### <a name="remarks"></a>Remarks

Когда пользователь сохраняет документ, приложение удаляет файл автоматического сохранения, поскольку он больше не нужен. `UpdateDocumentInfo`удаляет автосохраненный файл, [позвонив в CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo). `UpdateDocumentInfo`затем добавляет информацию из *pDocument* в список открытых в настоящее время документов, поскольку `RemoveDocumentInfo` удаляет эту информацию, но сохраненный документ все еще открыт.

Чтобы использовать этот метод, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES должны быть установлены в *m_dwRestartManagerSupportFlags.*

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Практическое руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)
