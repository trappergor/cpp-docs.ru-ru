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
ms.openlocfilehash: 5b4e39fa4d93893d288bb8de03d8a71b671be087
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497397"
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
Класс, производный от `CComCoClass`.

*пклсид*<br/>
Указатель на идентификатор CLSID объекта.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComCoClass:: CreateInstance](#createinstance)|Статически Создает экземпляр класса и запросы для интерфейса.|
|[CComCoClass:: Error](#error)|Статически Возвращает клиенту подробные сведения об ошибке.|
|[CComCoClass:: Жетобжектклсид](#getobjectclsid)|Статически Возвращает идентификатор класса объекта.|
|[CComCoClass:: Жетобжектдескриптион](#getobjectdescription)|Статически Переопределение для возврата описания объекта.|

## <a name="remarks"></a>Примечания

`CComCoClass`предоставляет методы для получения CLSID объекта, настройки сведений об ошибках и создания экземпляров класса. Любой класс, зарегистрированный в сопоставлении объектов, `CComCoClass`должен быть производным от.

`CComCoClass`также определяет фабрику класса по умолчанию и модель статистической обработки для объекта. `CComCoClass`использует следующие два макроса:

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) Объявляет фабрику класса для [ккомклассфактори](../../atl/reference/ccomclassfactory-class.md).

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) Объявляет, что объект может быть агрегирован.

Можно переопределить любое из этих значений по умолчанию, указав другой макрос в определении класса. Например, чтобы использовать [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) вместо `CComClassFactory`, укажите макрос [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) :

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="createinstance"></a>CComCoClass:: CreateInstance

Используйте эти `CreateInstance` функции для создания экземпляра COM-объекта и получения указателя интерфейса без использования API COM.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>Параметры

*Q*<br/>
COM-интерфейс, который должен возвращаться через *PP*.

*пункаутер*<br/>
окне Внешняя неизвестная или неизвестная функция управления статистической функцией.

*PP*<br/>
заполняет Адрес переменной указателя, которая получает запрошенный указатель интерфейса при успешности создания.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. Описание возможных возвращаемых значений см. в разделе [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) в Windows SDK.

### <a name="remarks"></a>Примечания

Используйте первую перегрузку этой функции для типичного создания объектов; Используйте вторую перегрузку, если необходимо выполнить статистическую обработку создаваемого объекта.

Класс ATL, реализующий требуемый COM-объект (то есть класс, используемый в качестве первого параметра шаблона для [CComCoClass](../../atl/reference/ccomcoclass-class.md)), должен находиться в том же проекте, что и вызывающий код. Создание COM-объекта выполняется фабрикой классов, зарегистрированной для этого класса ATL.

Эти функции удобно использовать для создания объектов, которые не могут быть созданы извне с помощью макроса [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) . Они также полезны в ситуациях, когда необходимо избежать COM-API для повышения эффективности.

Обратите внимание, что интерфейсу *Q* должен быть сопоставлен идентификатор IID, который можно получить с помощью оператора [__uuidof](../../cpp/uuidof-operator.md) .

### <a name="example"></a>Пример

В следующем примере `CDocument` — созданный мастером класс ATL, производный от `CComCoClass` , реализующий `IDocument` интерфейс. Класс регистрируется в сопоставлении объектов с помощью макроса OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO, поэтому клиенты не могут создавать экземпляры документа, используя [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance). `CApplication`— Это компонентный класс, предоставляющий метод для одного из своих собственных интерфейсов COM для создания экземпляров класса Document. В приведенном ниже коде показано, как легко создать экземпляры класса Document с помощью члена `CreateInstance` , унаследованного `CComCoClass` от базового класса.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

##  <a name="error"></a>CComCoClass:: Error

Эта статическая функция настраивает `IErrorInfo` интерфейс для предоставления клиенту сведений об ошибке.

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

*лпсздеск*<br/>
окне Строка, описывающая ошибку. Версия `Error` Юникода указывает, что *лпсздеск* имеет тип лпколестр; версия ANSI указывает тип LPCSTR.

*IID*<br/>
окне Идентификатор IID интерфейса, определяющего ошибку или GUID_NULL (значение по умолчанию), если ошибка определяется операционной системой.

*хрес*<br/>
окне Значение HRESULT, которое требуется вернуть вызывающему объекту. Значение по умолчанию — 0. Дополнительные сведения о *хрес*см. в разделе Примечания.

*nID*<br/>
окне Идентификатор ресурса, в котором хранится строка описания ошибки. Это значение должно находиться в диапазоне от 0x0200 до 0xFFFF включительно. В отладочных сборках оператор **Assert** приведет к тому, что *NID* не индексирует допустимую строку. В сборках выпуска для строки описания ошибки будет задано значение "Неизвестная ошибка".

*двхелпид*<br/>
окне Идентификатор контекста справки для ошибки.

*лпсзелпфиле*<br/>
окне Путь и имя файла справки, описывающего ошибку.

*хинст*<br/>
окне Маркер ресурса. По умолчанию этот параметр имеет `_AtlModule::GetResourceInstance`значение, `_AtlModule` где является глобальным экземпляром [катлмодуле](../../atl/reference/catlmodule-class.md).

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

Для вызова `Error`объект должен `ISupportErrorInfo Interface` реализовать интерфейс.

Если параметр *хрес* не равен нулю, `Error` возвращается значение *хрес*. Если *хрес* равен нулю, то первые четыре версии `Error` возвращают DISP_E_EXCEPTION. Последние две версии возвращают результат макроса **MAKE_HRESULT (1, FACILITY_ITF,** *NID* **)** .

##  <a name="getobjectclsid"></a>CComCoClass:: Жетобжектклсид

Обеспечивает согласованный способ получения CLSID объекта.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор класса объекта.

##  <a name="getobjectdescription"></a>CComCoClass:: Жетобжектдескриптион

Эта статическая функция получает текстовое описание для объекта класса.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>Возвращаемое значение

Описание объекта класса.

### <a name="remarks"></a>Примечания

Реализация по умолчанию возвращает значение NULL. Этот метод можно переопределить с помощью макроса [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) . Например:

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription`метод вызывается `IComponentRegistrar::GetComponents`методом. `IComponentRegistrar`— Это интерфейс автоматизации, позволяющий регистрировать и отменять регистрацию отдельных компонентов в библиотеке DLL. При создании объекта регистратора компонентов с помощью мастера проектов ATL мастер автоматически реализует `IComponentRegistrar` интерфейс. `IComponentRegistrar`обычно используется сервером транзакций Microsoft Transaction Server.

Дополнительные сведения о мастере проектов ATL см. в статье [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md).

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
