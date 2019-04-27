---
title: Класс CComCoClass
ms.date: 11/04/2016
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
ms.openlocfilehash: c52e1a95483807f9c842b0b904cd2314258f0e26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259876"
---
# <a name="ccomcoclass-class"></a>Класс CComCoClass

Этот класс предоставляет методы для создания экземпляров класса и получения его свойств.

## <a name="syntax"></a>Синтаксис

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `CComCoClass`.

*pclsid*<br/>
Указатель на идентификатор CLSID объекта.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComCoClass::CreateInstance](#createinstance)|(Статический) Создает экземпляр класса и запросы для интерфейса.|
|[CComCoClass::Error](#error)|(Статический) Возвращает сведения об ошибке клиенту.|
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(Статический) Возвращает идентификатор класса объекта.|
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(Статический) Переопределите для возврата описание объекта.|

## <a name="remarks"></a>Примечания

`CComCoClass` Предоставляет методы для получения CLSID объекта, настройки сведений об ошибках и создания экземпляров класса. Любой класс, который зарегистрирован в карте объектов должен быть производным от `CComCoClass`.

`CComCoClass` также определяет модель по умолчанию класс фабрики и статистическую обработку для объекта. `CComCoClass` использует следующие два макроса:

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) объявляет фабрики класса быть [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) объявляет, что объект может быть агрегировано.

Одно из этих умолчаний можно переопределить, указав другой макроса в определении класса. Например, чтобы использовать [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) вместо `CComClassFactory`, укажите [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) макрос:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="createinstance"></a>  CComCoClass::CreateInstance

Используйте эти `CreateInstance` функции для создания экземпляра COM и получите указатель интерфейса без использования COM API.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>Параметры

*Q*<br/>
COM-интерфейс, который должен возвращаться через *pp*.

*punkOuter*<br/>
[in] Внешняя Неизвестная строка или управляющий unknown агрегатной функции.

*PP*<br/>
[out] Адрес переменной указателя, получающей указатель запрошенный интерфейс в том случае, если успешно создана.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. См. в разделе [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance) в пакете SDK для Windows, описание возможные возвращаемые значения.

### <a name="remarks"></a>Примечания

Использовать первую перегрузку этой функции для создания типичных объекта; Используйте вторую перегрузку, когда просуммируйте создаваемый объект.

ATL-класс, реализующий необходимый объект COM (то есть класс, используемый как первый параметр шаблона для [CComCoClass](../../atl/reference/ccomcoclass-class.md)) должен быть в том же проекте, что вызывающий код. Создание COM-объекта, выполняемая процессом фабрики класса, зарегистрированные для этого класса ATL.

Эти функции полезны для создания объектов, которые запрещено быть внешне с помощью [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) макрос. Они также полезны в ситуациях, где вы хотите избежать API COM для повышения эффективности.

Обратите внимание, что интерфейс *Q* должен иметь связанный с ним IID, можно получить с помощью [__uuidof](../../cpp/uuidof-operator.md) оператор.

### <a name="example"></a>Пример

В следующем примере `CDocument` созданный мастером ATL класс, производный от `CComCoClass` , реализующий `IDocument` интерфейс. Класс регистрируется в карте объектов с помощью макроса OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO, поэтому клиенты не смогут создавать экземпляры документа с помощью [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance). `CApplication` Представляет компонентный класс, предоставляющий метод на одном из собственных интерфейсов COM, для создания экземпляров класса документа. В коде ниже показан как просто его, чтобы создать экземпляры класса документа с использованием `CreateInstance` член наследуется от `CComCoClass` базового класса.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

##  <a name="error"></a>  CComCoClass::Error

Настраивает эту статическую функцию `IErrorInfo` интерфейс для предоставления клиенту сведений об ошибке.

```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```

### <a name="parameters"></a>Параметры

*lpszDesc*<br/>
[in] Строка, описывающая ошибку. Версия Юникода `Error` указывает, что *lpszDesc* имеет тип LPCOLESTR; версия ANSI указывает тип LPCSTR.

*IID*<br/>
[in] Идентификатор IID интерфейса, определяющего GUID_NULL (значение по умолчанию) или ошибка, если ошибки определяется операционной системой.

*hRes*<br/>
[in] Значение HRESULT, который вы хотите возвращается вызывающей стороне. Значение по умолчанию — 0. Дополнительные сведения о *hRes*, см. в разделе "Примечания".

*nID*<br/>
[in] Идентификатор ресурса, где хранится строка описания ошибки. Это значение должно лежать между 0x0200 и 0xFFFF, включительно. В отладочных сборках **ASSERT** Если *nID* индекса не является допустимой строкой. Строка описания ошибки в сборках выпуска будет указано значение «Unknown Error».

*dwHelpID*<br/>
[in] Идентификатор контекста справки для ошибки.

*lpszHelpFile*<br/>
[in] Путь и имя файла справки, описывающий ошибку.

*hInst*<br/>
[in] Дескриптор для ресурса. По умолчанию этот параметр является `_AtlModule::GetResourceInstance`, где `_AtlModule` — это глобальный экземпляр [CAtlModule](../../atl/reference/catlmodule-class.md).

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

Для вызова `Error`, ваш объект должен реализовывать `ISupportErrorInfo Interface` интерфейс.

Если *hRes* параметра не равно нулю, затем `Error` возвращает значение *hRes*. Если *hRes* равно нулю, то в первых четырех версиях `Error` возвращает DISP_E_EXCEPTION. Две последние версии возвращают результат этого макроса **MAKE_HRESULT (1, FACILITY_ITF,** *nID* **)**.

##  <a name="getobjectclsid"></a>  CComCoClass::GetObjectCLSID

Предоставляет согласованный способ получения CLSID объекта.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор класса объекта.

##  <a name="getobjectdescription"></a>  CComCoClass::GetObjectDescription

Эта статическая функция извлекает текстовое описание для объекта класса.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>Возвращаемое значение

Описание класса объекта.

### <a name="remarks"></a>Примечания

Реализация по умолчанию возвращает значение NULL. Можно переопределить этот метод с [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) макрос. Пример:

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription` вызывается `IComponentRegistrar::GetComponents`. `IComponentRegistrar` представляет собой интерфейс автоматизации для регистрации и отмены регистрации отдельных компонентов в библиотеке DLL. При создании объекта регистрации компонента с помощью мастера проектов ATL, мастер будет автоматически реализовывать `IComponentRegistrar` интерфейс. `IComponentRegistrar` обычно используется сервером транзакций.

Дополнительные сведения о мастере проекта ATL, см. в статье [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md).

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
