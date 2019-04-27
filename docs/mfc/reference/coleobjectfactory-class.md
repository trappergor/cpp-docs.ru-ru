---
title: Coleobjectfactory-класс
ms.date: 11/04/2016
f1_keywords:
- COleObjectFactory
- AFXDISP/COleObjectFactory
- AFXDISP/COleObjectFactory::COleObjectFactory
- AFXDISP/COleObjectFactory::GetClassID
- AFXDISP/COleObjectFactory::IsLicenseValid
- AFXDISP/COleObjectFactory::IsRegistered
- AFXDISP/COleObjectFactory::Register
- AFXDISP/COleObjectFactory::RegisterAll
- AFXDISP/COleObjectFactory::Revoke
- AFXDISP/COleObjectFactory::RevokeAll
- AFXDISP/COleObjectFactory::UnregisterAll
- AFXDISP/COleObjectFactory::UpdateRegistry
- AFXDISP/COleObjectFactory::UpdateRegistryAll
- AFXDISP/COleObjectFactory::GetLicenseKey
- AFXDISP/COleObjectFactory::OnCreateObject
- AFXDISP/COleObjectFactory::VerifyLicenseKey
- AFXDISP/COleObjectFactory::VerifyUserLicense
helpviewer_keywords:
- COleObjectFactory [MFC], COleObjectFactory
- COleObjectFactory [MFC], GetClassID
- COleObjectFactory [MFC], IsLicenseValid
- COleObjectFactory [MFC], IsRegistered
- COleObjectFactory [MFC], Register
- COleObjectFactory [MFC], RegisterAll
- COleObjectFactory [MFC], Revoke
- COleObjectFactory [MFC], RevokeAll
- COleObjectFactory [MFC], UnregisterAll
- COleObjectFactory [MFC], UpdateRegistry
- COleObjectFactory [MFC], UpdateRegistryAll
- COleObjectFactory [MFC], GetLicenseKey
- COleObjectFactory [MFC], OnCreateObject
- COleObjectFactory [MFC], VerifyLicenseKey
- COleObjectFactory [MFC], VerifyUserLicense
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
ms.openlocfilehash: 25dce92f49ba9de08fcf33d54db8e97d520f5ea4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224394"
---
# <a name="coleobjectfactory-class"></a>Coleobjectfactory-класс

Реализует фабрику класса OLE, которая создает OLE-объекты, такие как серверы, объекты автоматизации и документы.

## <a name="syntax"></a>Синтаксис

```
class COleObjectFactory : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|Создает объект `COleObjectFactory`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleObjectFactory::GetClassID](#getclassid)|КОД объектов, создаваемых данной фабрикой класса возвращает OLE.|
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Определяет, является ли допустимым лицензии элемента управления.|
|[COleObjectFactory::IsRegistered](#isregistered)|Указывает, зарегистрировано ли фабрику объектов OLE системные библиотеки DLL.|
|[Команда COleObjectFactory::Register](#register)|Регистрирует этот фабрику объектов OLE системные библиотеки DLL.|
|[COleObjectFactory::RegisterAll](#registerall)|Регистрирует все фабрики приложения объекта OLE системных библиотек DLL.|
|[COleObjectFactory::Revoke](#revoke)|Отменяет регистрацию фабрику объектов OLE системные библиотеки DLL.|
|[COleObjectFactory::RevokeAll](#revokeall)|Отменяет регистрации фабрики объект приложения с OLE системные библиотеки DLL.|
|[COleObjectFactory::UnregisterAll](#unregisterall)|Отменяет регистрацию всех фабрик объектов приложения.|
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Регистрирует фабрику этот объект в системном реестре OLE.|
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|Регистрирует все приложения объект фабрики в системном реестре OLE.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Запрашивает уникальный ключ из библиотеки DLL элемента управления.|
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Вызывается платформой для создания нового объекта типа этой фабрики.|
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Проверяет соответствие ключами, внедренными в элементе управления ключами, внедренными в контейнере.|
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Проверяет, что элемент управления есть лицензия для использования во время разработки.|

## <a name="remarks"></a>Примечания

`COleObjectFactory` Класс содержит функции-члены для выполнения следующих функций:

- Управление регистрацией объектов.

- Обновление регистрации системы OLE, а также регистрации во время выполнения, который информирует OLE, что объекты, работающих под управлением и подготовлены для получения сообщений.

- Применение лицензирования путем ограничения использования элемента управления для лицензированных разработчиков во время разработки и для лицензированных приложений во время выполнения.

- Регистрация фабрик объектов управления в системном реестре OLE.

Дополнительные сведения о создании объекта, см. в статьях [объекты данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md) и [объекты и источники данных: Создание и уничтожение](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Дополнительные сведения о регистрации, см. в статье [регистрации](../../mfc/registration.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleObjectFactory`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory

Создает `COleObjectFactory` , инициализирует его как фабрику объектов для отмены регистрации и добавляет его в список фабрик.

```
COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    LPCTSTR lpszProgID);

COleObjectFactory(
    REFCLSID clsid,
    CRuntimeClass* pRuntimeClass,
    BOOL bMultiInstance,
    int nFlags,
    LPCTSTR lpszProgID);
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
Ссылка на идентификатор класса OLE, который представляет этот объект фабрики.

*pRuntimeClass*<br/>
Указатель на класс времени выполнения объектов C++, создаваемых данной фабрикой.

*bMultiInstance*<br/>
Указывает, является ли один экземпляр приложения может поддерживать несколько экземпляров. Значение TRUE, если несколько экземпляров приложения запускаются для каждого запроса для создания объекта.

*nFlags*<br/>
Содержит один или несколько из следующих флагов:

- `afxRegDefault` Задает модель потоков для ThreadingModel = подразделения.

- `afxRegInsertable` Позволяет элементу управления отображаются в **вставить объект** диалоговое окно для объектов OLE.

- `afxRegApartmentThreading` Задает модель потоков в реестре ThreadingModel = подразделения.

- `afxRegFreeThreading` Задает модель потоков в реестре ThreadingModel = Free.

   Вы можете объединить два флага `afxRegApartmentThreading` и `afxRegFreeThreading` присвоить ThreadingModel = Both. См. в разделе [InprocServer32](/windows/desktop/com/inprocserver32) в пакете SDK для Windows, Дополнительные сведения по использованию потоков регистрации модели.

*lpszProgID*<br/>
Указатель на строку, содержащую идентификатор устные программы, такие как «Microsoft Excel».

### <a name="remarks"></a>Примечания

Чтобы использовать объект, тем не менее, необходимо зарегистрировать его.

Дополнительные сведения см. в разделе [раздел CLSID](/windows/desktop/com/clsid-key-hklm) в пакете Windows SDK.

##  <a name="getclassid"></a>  COleObjectFactory::GetClassID

Возвращает ссылку на идентификатор класса OLE, который представляет эта фабрика.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Представляет ссылку на идентификатор класса OLE этой фабрики.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [раздел CLSID](/windows/desktop/com/clsid-key-hklm) в пакете Windows SDK.

##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey

Запрашивает уникальное лицензионного ключа из библиотеки DLL элемента управления и сохраняет его в строку BSTR, на которые указывают *pbstrKey*.

```
virtual BOOL GetLicenseKey(
    DWORD dwReserved,
    BSTR* pbstrKey);
```

### <a name="parameters"></a>Параметры

*dwReserved*<br/>
Зарезервировано для будущего использования.

*pbstrKey*<br/>
Указатель на строку BSTR, в которой будут храниться лицензионный ключ.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если строка лицензионный ключ не имеет значение NULL; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция возвращает значение 0 и сохраняет ничего не в строку BSTR. Если вы используете автоматически ActiveX MFC для создания проекта, автоматически предоставляет переопределения, которое извлекает ключ лицензии для элемента управления.

##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid

Определяет, является ли допустимым лицензии элемента управления.

```
BOOL IsLicenseValid();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если successul; в противном случае — false.

##  <a name="isregistered"></a>  COleObjectFactory::IsRegistered

Возвращает ненулевое значение, если фабрика зарегистрирована OLE системные библиотеки DLL.

```
virtual BOOL IsRegistered() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрика зарегистрирована; в противном случае 0.

##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject

Вызывается платформой для создания нового объекта.

```
virtual CCmdTarget* OnCreateObject();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на созданный объект. Он может вызывать исключение, памяти, если происходит сбой.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для создания объекта из что-то отличное от [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) передается конструктору.

##  <a name="register"></a>  Команда COleObjectFactory::Register

Регистрирует этот фабрику объектов OLE системные библиотеки DLL.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрика успешно зарегистрирована; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается средой [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.

##  <a name="registerall"></a>  COleObjectFactory::RegisterAll

Регистрирует все фабрики приложения объекта OLE системные библиотеки DLL.

```
static BOOL PASCAL RegisterAll();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрик успешно зарегистрировано; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается средой [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.

##  <a name="revoke"></a>  COleObjectFactory::Revoke

Отменяет регистрацию фабрику объектов OLE системные библиотеки DLL.

```
void Revoke();
```

### <a name="remarks"></a>Примечания

Платформа автоматически вызывает эту функцию перед завершением работы приложения. При необходимости вызовите его из переопределения [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll

Отменяет все регистрации приложения объект фабрики с OLE системные библиотеки DLL.

```
static void PASCAL RevokeAll();
```

### <a name="remarks"></a>Примечания

Платформа автоматически вызывает эту функцию перед завершением работы приложения. При необходимости вызовите его из переопределения [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

##  <a name="unregisterall"></a>  COleObjectFactory::UnregisterAll

Отменяет регистрацию всех фабрик объектов приложения.

```
static BOOL PASCAL UnregisterAll();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

##  <a name="updateregistry"></a>  COleObjectFactory::UpdateRegistry

Регистрирует все приложения объект фабрики в системном реестре OLE.

```
void UpdateRegistry(LPCTSTR lpszProgID = NULL);
virtual BOOL UpdateRegistry(BOOL bRegister);
```

### <a name="parameters"></a>Параметры

*lpszProgID*<br/>
Указатель на строку, содержащую удобное для восприятия программный идентификатор, например «Excel.Document.5.»

*bЗарегистрируйтесь участия*<br/>
Определяет, является ли класс элемента управления фабрику объектов для регистрации.

### <a name="remarks"></a>Примечания

Выполните краткие обсуждения из двух форм для этой функции.

- **UpdateRegistry (** `lpszProgID` **)** регистрирует этот объект фабрики в системном реестре OLE. Эта функция обычно вызывается средой [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.

- **UpdateRegistry (** `bRegister` **)** эту форму функции является переопределяемым. Если *bЗарегистрируйтесь участия* имеет значение TRUE, это действие регистрирует функцию управления класса в системном реестре. В противном случае он отменяет регистрацию класса.

   Если вы используете автоматически ActiveX MFC для создания проекта, автоматически предоставляет переопределение, чтобы этот чистой виртуальной функции.

##  <a name="updateregistryall"></a>  COleObjectFactory::UpdateRegistryAll

Регистрирует все приложения объект фабрики в системном реестре OLE.

```
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Параметры

*bЗарегистрируйтесь участия*<br/>
Определяет, является ли класс элемента управления фабрику объектов для регистрации.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрик успешно обновлены; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается средой [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.

##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey

Проверяет, что контейнер есть лицензия на использование элемента управления OLE.

```
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```

### <a name="parameters"></a>Параметры

*bstrKey*<br/>
BSTR, хранение контейнера версию строки лицензии.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если лицензия времени выполнения является допустимым; в противном случае 0.

### <a name="remarks"></a>Примечания

Версия по умолчанию вызывает [GetLicenseKey](#getlicensekey) для получения копии элемента управления в лицензии строку и сравнивает его со строки в *bstrKey*. Если две строки совпадают, функция возвращает ненулевое значение; в противном случае она возвращает 0.

Можно переопределить эту функцию для предоставления настроенным проверочным лицензии.

Функция [VerifyUserLicense](#verifyuserlicense) проверяет лицензий во время разработки.

##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense

Проверка лицензий во время разработки для элемента управления OLE.

```
virtual BOOL VerifyUserLicense();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если во время разработки лицензия действительна; в противном случае 0.

## <a name="see-also"></a>См. также

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
