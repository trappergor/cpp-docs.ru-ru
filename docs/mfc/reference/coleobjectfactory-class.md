---
title: Класс COleObjectFactory
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
ms.openlocfilehash: 22805550d13ecb400b151495363e5eda2dfb3b76
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503741"
---
# <a name="coleobjectfactory-class"></a>Класс COleObjectFactory

Реализует фабрику класса OLE, которая создает OLE-объекты, такие как серверы, объекты автоматизации и документы.

## <a name="syntax"></a>Синтаксис

```
class COleObjectFactory : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleObjectFactory:: COleObjectFactory](#coleobjectfactory)|Создает объект `COleObjectFactory`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleObjectFactory::, ClassID](#getclassid)|Возвращает идентификатор класса OLE объектов, создаваемых этой фабрикой.|
|[COleObjectFactory:: Ислиценсевалид](#islicensevalid)|Определяет, является ли действительная лицензия элемента управления.|
|[COleObjectFactory:: Register](#isregistered)|Указывает, зарегистрирована ли фабрика объектов в системных библиотеках DLL OLE.|
|[COleObjectFactory:: Register](#register)|Регистрирует эту фабрику объектов в DLL-библиотеках системы OLE.|
|[COleObjectFactory:: Регистералл](#registerall)|Регистрирует все фабрики объектов приложения с помощью системных библиотек OLE.|
|[COleObjectFactory:: REVOKE](#revoke)|Отменяет регистрацию этой фабрики объектов с помощью библиотек DLL системы OLE.|
|[COleObjectFactory:: Ревокеалл](#revokeall)|Отменяет регистрацию фабрик объектов приложения с помощью библиотек DLL системы OLE.|
|[COleObjectFactory:: Унрегистералл](#unregisterall)|Отменяет регистрацию всех фабрик объектов приложения.|
|[COleObjectFactory:: UpdateRegistry](#updateregistry)|Регистрирует эту фабрику объектов в системном реестре OLE.|
|[COleObjectFactory:: UpdateRegistryAll](#updateregistryall)|Регистрирует все фабрики объектов приложения с помощью системного реестра OLE.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[COleObjectFactory:: Жетлиценсекэй](#getlicensekey)|Запрашивает уникальный ключ из библиотеки DLL элемента управления.|
|[COleObjectFactory:: oncreateobject](#oncreateobject)|Вызывается платформой для создания нового объекта типа фабрики.|
|[COleObjectFactory:: Верифилиценсекэй](#verifylicensekey)|Проверяет, соответствует ли ключ, внедренный в элементе управления, ключу, внедренному в контейнер.|
|[COleObjectFactory:: Верифюсерлиценсе](#verifyuserlicense)|Проверяет, что элемент управления лицензирован для использования во время разработки.|

## <a name="remarks"></a>Примечания

`COleObjectFactory` Класс содержит функции элементов для выполнения следующих функций:

- Управление регистрацией объектов.

- Обновление системного регистра OLE, а также регистрация времени выполнения, которая информирует OLE о том, что объекты запущены и готовы к получению сообщений.

- Обеспечение лицензирования путем ограничения использования элемента управления лицензированными разработчиками во время разработки и лицензированными приложениями во время выполнения.

- Регистрация фабрик управляющих объектов с помощью системного реестра OLE.

Дополнительные сведения о создании объектов см. в статьях [объекты данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md) и [объекты данных и источники данных. Создание и уничтожение](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Дополнительные сведения о регистрации см. в статье [Регистрация](../../mfc/registration.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleObjectFactory`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="coleobjectfactory"></a>COleObjectFactory:: COleObjectFactory

`COleObjectFactory` Создает объект, инициализирует его как незарегистрированную фабрику объектов и добавляет ее в список фабрик.

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

*этому*<br/>
Ссылка на идентификатор класса OLE, который представляет эта фабрика объектов.

*прунтимекласс*<br/>
Указатель на класс времени выполнения объектов, C++ которые может создать эта фабрика.

*Bmultiinstance конструктору*<br/>
Указывает, может ли один экземпляр приложения поддерживать несколько экземпляров. Если значение — TRUE, для каждого запроса на создание объекта запускается несколько экземпляров приложения.

*нфлагс*<br/>
Содержит один или несколько следующих флагов:

- `afxRegDefault`Задает для потоковой модели значение ThreadingModel = апартамент.

- `afxRegInsertable`Разрешает отображение элемента управления в диалоговом окне « **Вставка объекта** » для объектов OLE.

- `afxRegApartmentThreading`Задает для потоковой модели в реестре значение ThreadingModel = апартамент.

- `afxRegFreeThreading`Задает для потоковой модели в реестре значение ThreadingModel = Free.

   Можно объединить два флага `afxRegApartmentThreading` и `afxRegFreeThreading` задать ThreadingModel = оба. Дополнительные сведения о регистрации модели потоков см. в разделе [InprocServer32](/windows/win32/com/inprocserver32) в Windows SDK.

*лпсзпрогид*<br/>
Указатель на строку, содержащую идентификатор программы текстовом, например Microsoft Excel.

### <a name="remarks"></a>Примечания

Однако для использования объекта его необходимо зарегистрировать.

Дополнительные сведения см. в разделе [ключ CLSID](/windows/win32/com/clsid-key-hklm) в Windows SDK.

##  <a name="getclassid"></a>COleObjectFactory::, ClassID

Возвращает ссылку на идентификатор класса OLE, который представляет эта фабрика.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на идентификатор класса OLE, который представляет эта фабрика.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ключ CLSID](/windows/win32/com/clsid-key-hklm) в Windows SDK.

##  <a name="getlicensekey"></a>COleObjectFactory:: Жетлиценсекэй

Запрашивает уникальный лицензионный ключ из библиотеки DLL элемента управления и сохраняет его в строке BSTR, на которую указывает *пбстркэй*.

```
virtual BOOL GetLicenseKey(
    DWORD dwReserved,
    BSTR* pbstrKey);
```

### <a name="parameters"></a>Параметры

*двресервед*<br/>
Зарезервировано для будущего использования.

*пбстркэй*<br/>
Указатель на BSTR, в котором будет храниться лицензионный ключ.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если строка ключа лицензии не равна NULL; в противном случае — 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции возвращает 0, и в BSTR ничего не сохраняется. Если вы используете MFC ActiveX Контролвизард для создания проекта, Контролвизард предоставляет переопределение, которое получает ключ лицензии элемента управления.

##  <a name="islicensevalid"></a>COleObjectFactory:: Ислиценсевалид

Определяет, является ли действительная лицензия элемента управления.

```
BOOL IsLicenseValid();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если сукцессул; в противном случае — false.

##  <a name="isregistered"></a>COleObjectFactory:: Register

Функция возвращает ненулевое значение, если фабрика зарегистрирована в системных библиотеках DLL OLE.

```
virtual BOOL IsRegistered() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрика зарегистрирована; в противном случае — 0.

##  <a name="oncreateobject"></a>COleObjectFactory:: oncreateobject

Вызывается платформой для создания нового объекта.

```
virtual CCmdTarget* OnCreateObject();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на созданный объект. В случае сбоя он может вызвать исключение памяти.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы создать объект из чего-либо, отличного от [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , переданного в конструктор.

##  <a name="register"></a>COleObjectFactory:: Register

Регистрирует эту фабрику объектов в DLL-библиотеках системы OLE.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрика успешно зарегистрирована; в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается методом [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.

##  <a name="registerall"></a>COleObjectFactory:: Регистералл

Регистрирует все фабрики объектов приложения с помощью системных библиотек OLE.

```
static BOOL PASCAL RegisterAll();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрики успешно зарегистрированы; в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается методом [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.

##  <a name="revoke"></a>COleObjectFactory:: REVOKE

Отменяет регистрацию этой фабрики объектов с помощью библиотек DLL системы OLE.

```
void Revoke();
```

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию автоматически перед завершением приложения. При необходимости вызовите его из переопределения [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

##  <a name="revokeall"></a>COleObjectFactory:: Ревокеалл

Отменяет все регистрации фабрики объектов приложения с помощью системных библиотек OLE.

```
static void PASCAL RevokeAll();
```

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию автоматически перед завершением приложения. При необходимости вызовите его из переопределения [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).

##  <a name="unregisterall"></a>COleObjectFactory:: Унрегистералл

Отменяет регистрацию всех фабрик объектов приложения.

```
static BOOL PASCAL UnregisterAll();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

##  <a name="updateregistry"></a>COleObjectFactory:: UpdateRegistry

Регистрирует все фабрики объектов приложения с помощью системного реестра OLE.

```
void UpdateRegistry(LPCTSTR lpszProgID = NULL);
virtual BOOL UpdateRegistry(BOOL bRegister);
```

### <a name="parameters"></a>Параметры

*лпсзпрогид*<br/>
Указатель на строку, содержащую идентификатор программы, доступной для чтения, например Excel. Document. 5.

*брегистер*<br/>
Определяет, должна ли быть зарегистрирована фабрика объектов класса элемента управления.

### <a name="remarks"></a>Примечания

Краткие обсуждения двух форм для этой функции:

- **UpdateRegistry (** `lpszProgID` **)** регистрирует эту фабрику объектов в системном реестре OLE. Эта функция обычно вызывается методом [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.

- **UpdateRegistry (** `bRegister` **)** . Эта форма функции является переопределяемой. Если *брегистер* имеет значение true, эта функция регистрирует класс элемента управления в системном реестре. В противном случае он отменяет регистрацию класса.

   Если вы используете MFC ActiveX Контролвизард для создания проекта, Контролвизард предоставляет переопределение для этой чистой виртуальной функции.

##  <a name="updateregistryall"></a>COleObjectFactory:: UpdateRegistryAll

Регистрирует все фабрики объектов приложения с помощью системного реестра OLE.

```
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```

### <a name="parameters"></a>Параметры

*брегистер*<br/>
Определяет, должна ли быть зарегистрирована фабрика объектов класса элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрики успешно обновлены; в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается методом [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.

##  <a name="verifylicensekey"></a>COleObjectFactory:: Верифилиценсекэй

Проверяет, имеет ли контейнер лицензию на использование элемента управления OLE.

```
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```

### <a name="parameters"></a>Параметры

*бстркэй*<br/>
Значение BSTR, в котором хранится версия строки лицензии контейнера.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если лицензия времени выполнения действительна; в противном случае — 0.

### <a name="remarks"></a>Примечания

Версия по умолчанию вызывает [жетлиценсекэй](#getlicensekey) , чтобы получить копию строки лицензии элемента управления и сравнивает ее со строкой в *бстркэй*. Если две строки совпадают, функция возвращает ненулевое значение. в противном случае возвращается значение 0.

Эту функцию можно переопределить, чтобы предоставить настраиваемую проверку лицензии.

Функция [верифюсерлиценсе](#verifyuserlicense) проверяет лицензию времени разработки.

##  <a name="verifyuserlicense"></a>COleObjectFactory:: Верифюсерлиценсе

Проверяет лицензию времени разработки для элемента управления OLE.

```
virtual BOOL VerifyUserLicense();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если лицензия времени разработки действительна; в противном случае — 0.

## <a name="see-also"></a>См. также

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
