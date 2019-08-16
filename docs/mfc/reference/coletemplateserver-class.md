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
ms.openlocfilehash: 4a1997497f3bddb405b712b5534f76e577dabfa8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503084"
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
|[COleTemplateServer:: COleTemplateServer](#coletemplateserver)|Создает объект `COleTemplateServer`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleTemplateServer:: Коннекттемплате](#connecttemplate)|Подключает шаблон документа к базовому `COleObjectFactory` объекту.|
|[COleTemplateServer:: Отмена регистрации](#unregister)|Отменяет регистрацию связанного шаблона документа.|
|[COleTemplateServer:: UpdateRegistry](#updateregistry)|Регистрирует тип документа в системном реестре OLE.|

## <a name="remarks"></a>Примечания

Этот класс является производным от класса [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); обычно можно использовать `COleTemplateServer` напрямую, а не создавать собственный класс. `COleTemplateServer`использует объект [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) для управления серверными документами. Используется `COleTemplateServer` при реализации полного сервера, то есть сервера, который можно запустить как автономное приложение. Полные серверы обычно являются приложениями многодокументного интерфейса (MDI), хотя поддерживаются приложения с одним документом (SDI). Один `COleTemplateServer` объект необходим для каждого типа серверного документа, поддерживаемого приложением. то есть если серверное приложение поддерживает как листы, так и диаграммы, необходимо иметь два `COleTemplateServer` объекта.

`COleTemplateServer`переопределяет функцию `COleObjectFactory`члена,определенную `OnCreateInstance` . Эта функция-член вызывается платформой для создания C++ объекта соответствующего типа.

Дополнительные сведения о серверах см. в статье [серверы: Реализация сервера](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)

`COleTemplateServer`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="coletemplateserver"></a>COleTemplateServer:: COleTemplateServer

Создает объект `COleTemplateServer`.

```
COleTemplateServer();
```

### <a name="remarks"></a>Примечания

Краткое описание использования `COleTemplateServer` класса см. в разделе Общие сведения о классе [колелинкингдок](../../mfc/reference/colelinkingdoc-class.md) .

##  <a name="connecttemplate"></a>COleTemplateServer:: Коннекттемплате

Подключает шаблон документа, на который указывает *пдоктемплате* , к базовому объекту [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) .

```
void ConnectTemplate(
    REFCLSID clsid,
    CDocTemplate* pDocTemplate,
    BOOL bMultiInstance);
```

### <a name="parameters"></a>Параметры

*этому*<br/>
Ссылка на идентификатор класса OLE, который запрашивает шаблон.

*пдоктемплате*<br/>
Указатель на шаблон документа.

*Bmultiinstance конструктору*<br/>
Указывает, может ли один экземпляр приложения поддерживать несколько экземпляров. Если значение — TRUE, для каждого запроса на создание объекта запускается несколько экземпляров приложения.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ключ CLSID](/windows/win32/com/clsid-key-hklm) в Windows SDK.

##  <a name="unregister"></a>COleTemplateServer:: Отмена регистрации

Отменяет регистрацию связанного шаблона документа.

```
BOOL Unregister();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

ентерремаркс

##  <a name="updateregistry"></a>COleTemplateServer:: UpdateRegistry

Загружает сведения о типе файла из строки шаблона документа и помещает их в системный реестр OLE.

```
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL,
    BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Параметры

*напптипе*<br/>
Значение из перечисления OLE_APPTYPE, которое определено в АФКСДИСП. Высоты. Он может иметь одно из следующих значений:

- Сервер OAT_INPLACE_SERVER имеет полный пользовательский интерфейс сервера.

- Сервер OAT_SERVER поддерживает только внедрение.

- Контейнер OAT_CONTAINER поддерживает ссылки на внедренные объекты.

- Объект OAT_DISPATCH_OBJECT поддерживается `IDispatch`.

- Сервер OAT_DOC_OBJECT_SERVER поддерживает внедрение и модель компонентов объектов документов.

*рглпсзрегистер*<br/>
Список записей, которые записываются в реестр только в том случае, если ни одна запись не существует.

*рглпсзоверврите*<br/>
Список записей, записываемых в реестр независимо от того, существуют ли предыдущие записи.

*брегистер*<br/>
Определяет, должен ли быть зарегистрирован класс. Если *брегистер* имеет значение true, класс регистрируется в системном реестре. В противном случае он отменяет регистрацию класса.

### <a name="remarks"></a>Примечания

Сведения о регистрации загружаются посредством вызова [CDocTemplate:: жетдокстринг](../../mfc/reference/cdoctemplate-class.md#getdocstring). Извлекаемые подстроки — это те, которые определены `regFileTypeId`индексами `regFileTypeName`, и `fileNewName`, как описано на `GetDocString` страницах справочника.

Если подстрока пуста или если `GetDocString` вызов завершается неудачей по какой-либо другой причине, эта функция завершается ошибкой и сведения о файле не вносятся в реестр. `regFileTypeId`

Сведения в аргументах *рглпсзрегистер* и *рглпсзоверврите* записываются в реестр с помощью вызова [афксолерегистерсерверкласс](application-control.md#afxoleregisterserverclass). Сведения по умолчанию, которые регистрируются, если два аргумента имеют значение NULL, подходят для большинства приложений. Сведения о структуре данных в этих аргументах см. в разделе `AfxOleRegisterServerClass`.

Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

## <a name="see-also"></a>См. также

[Пример MFC для примера HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)<br/>
[Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)
