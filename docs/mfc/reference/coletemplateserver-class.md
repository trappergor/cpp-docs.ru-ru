---
title: Класс COleTemplateServer
ms.date: 11/04/2016
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
helpviewer_keywords:
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
ms.openlocfilehash: 3abdf1dc2da5ef9a111371b501d5cd8ce208825d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373557"
---
# <a name="coletemplateserver-class"></a>Класс COleTemplateServer

Используется для OLE-серверов визуального редактирования, серверов автоматизации и контейнеров связей (приложений, поддерживающих ссылки на внедряемые объекты).

## <a name="syntax"></a>Синтаксис

```
class COleTemplateServer : public COleObjectFactory
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|Создает объект `COleTemplateServer`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Подключается к основной шаблон документа `COleObjectFactory` объекта.|
|[COleTemplateServer::Unregister](#unregister)|Отменяет регистрацию шаблона связанный документ.|
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Регистрирует тип документа в системном реестре OLE.|

## <a name="remarks"></a>Примечания

Этот класс является производным от класса [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); как правило, можно использовать `COleTemplateServer` напрямую, вместо создания собственного производного класса. `COleTemplateServer` использует [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объект для управления документами сервера. Используйте `COleTemplateServer` при реализации полный сервер, то есть сервер, могут выполняться как отдельное приложение. Полный серверы обычно являются несколько приложений интерфейса (MDI) документа, несмотря на то, что поддерживаются приложения с интерфейсом (SDI) одного документа. Один `COleTemplateServer` для каждого типа документа сервер поддерживает приложения требуется объект; то есть, если серверное приложение поддерживает листы и диаграммы, необходимо иметь два `COleTemplateServer` объектов.

`COleTemplateServer` переопределяет `OnCreateInstance` определяется функция-член `COleObjectFactory`. Эта функция-член вызывается платформой для создания объекта C++ соответствующего типа.

Дополнительные сведения о серверах см. в статье [серверов: Реализация сервера](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="coletemplateserver"></a>  COleTemplateServer::COleTemplateServer

Создает объект `COleTemplateServer`.

```
COleTemplateServer();
```

### <a name="remarks"></a>Примечания

Краткое описание использования `COleTemplateServer` , представлена в разделе [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) Общие сведения о классе.

##  <a name="connecttemplate"></a>  COleTemplateServer::ConnectTemplate

Подключает шаблон документа, на которые указывают *pDocTemplate* к базовому объекту [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) объекта.

```
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
Ссылка на идентификатор класса OLE, который запрашивает шаблон.

*pDocTemplate*<br/>
Указатель на шаблон документа.

*bMultiInstance*<br/>
Указывает, является ли один экземпляр приложения может поддерживать несколько экземпляров. Значение TRUE, если несколько экземпляров приложения запускаются для каждого запроса для создания объекта.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [раздел CLSID](/windows/desktop/com/clsid-key-hklm) в пакете Windows SDK.

##  <a name="unregister"></a>  COleTemplateServer::Unregister

Отменяет регистрацию шаблона связанный документ.

```
BOOL Unregister();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

EnterRemarks

##  <a name="updateregistry"></a>  COleTemplateServer::UpdateRegistry

Загружает сведения о типе файла из строки шаблонов документов и помещает эту информацию в системном реестре OLE.

```
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Параметры

*nAppType*<br/>
Значение из перечисления OLE_APPTYPE, который определен в AFXDISP. З. Он может содержать любое из следующих значений:

- OAT_INPLACE_SERVER сервер имеет полный сервер пользовательского интерфейса.

- OAT_SERVER сервер поддерживает только внедрения.

- OAT_CONTAINER контейнер поддерживает ссылки на внедренные объекты.

- Объект OAT_DISPATCH_OBJECT `IDispatch`-поддержкой.

- OAT_DOC_OBJECT_SERVER Server поддерживает как встраивание и объект "документ" модели компонентов.

*rglpszRegister*<br/>
Список записей, которые записываются в реестр только в том случае, если нет никаких записей.

*rglpszOverwrite*<br/>
Список записей, которые записываются в реестр, независимо от того, существуют ли какие-либо предыдущей записи.

*bЗарегистрируйтесь участия*<br/>
Определяет, является ли класс для регистрации. Если *bЗарегистрируйтесь участия* имеет значение TRUE, класс регистрируется в системном реестре. В противном случае он отменяет регистрацию класса.

### <a name="remarks"></a>Примечания

Сведения о регистрации загружается посредством вызова [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Получить подстроки являются обозначенные индексы `regFileTypeId`, `regFileTypeName`, и `fileNewName`, как описано в `GetDocString` на страницах справки.

Если `regFileTypeId` подстроки пуст или если вызов `GetDocString` завершается ошибкой по любой другой причине, эта функция завершается ошибкой и данные файла не занесен в реестр.

Сведения в аргументах *rglpszRegister* и *rglpszOverwrite* записывается в реестр посредством вызова [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). Сведения по умолчанию, который регистрируется, когда два аргумента имеют значение NULL, подходит для большинства приложений. Сведения о структуре информации из этих аргументов, см. в разделе `AfxOleRegisterServerClass`.

Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

## <a name="see-also"></a>См. также

[Пример MFC HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)<br/>
[Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)
