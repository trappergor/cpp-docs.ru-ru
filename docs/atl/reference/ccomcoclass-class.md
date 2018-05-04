---
title: Класс CComCoClass | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
dev_langs:
- C++
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 738d7e937acf2d3299be97b4f091c698582911d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ccomcoclass-class"></a>Класс CComCoClass
Этот класс предоставляет методы для создания экземпляров класса и получения ее свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T, const CLSID* pclsid = &CLSID_NULL>  
class CComCoClass
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `CComCoClass`.  
  
 *pclsid*  
 Указатель на идентификатор CLSID объекта.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCoClass::CreateInstance](#createinstance)|(Статический) Создает экземпляр класса и запрашивает интерфейс.|  
|[CComCoClass::Error](#error)|(Статический) Возвращает сведения об ошибке клиенту.|  
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(Статический) Возвращает идентификатор класса объекта.|  
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(Статический) Переопределите для возврата описание объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CComCoClass` Предоставляет методы для получения CLSID объекта, настройки сведений об ошибках и создания экземпляров класса. Любой класс зарегистрирован в [схеме объекта](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f) должен быть производным от `CComCoClass`.  
  
 `CComCoClass` также определяет модель по умолчанию класс фабрики и статистической обработки для объекта. `CComCoClass` использует следующие два макроса:  
  
- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) объявляет фабрики класса, чтобы быть [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).  
  
- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) объявляет, что объект может быть статистически вычислена.  
  
 Одно из этих значений по умолчанию можно переопределить, указав другой макроса в определении класса. Например, чтобы использовать [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) вместо `CComClassFactory`, укажите [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) макрос:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="createinstance"></a>  CComCoClass::CreateInstance  
 Используйте эти `CreateInstance` функции для создания экземпляра COM объекта и получить указатель на интерфейс без использования COM API.  
  
```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `Q`  
 COM-интерфейс, который должен быть возвращен через `pp`.  
  
 *punkOuter*  
 [in] Внешняя Неизвестная строка или управляющий unknown агрегатной функции.  
  
 `pp`  
 [out] Адрес переменной указателя, которая получает указатель на запрошенный интерфейс при успешном создании.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` . В разделе [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) в Windows SDK описание возможные возвращаемые значения.  
  
### <a name="remarks"></a>Примечания  
 Используйте первой перегрузке этой функции для создания обычной объектов; Используйте вторую перегрузку, если требуются статистические значения с создаваемым объектом.  
  
 ATL класс, реализующий необходимые COM-объект (то есть класс, используемый как первый параметр шаблона [CComCoClass](../../atl/reference/ccomcoclass-class.md)) должен находиться в том же проекте, что и вызывающий код. Создание COM-объекта, выполняемые зарегистрирован для этого класса ATL фабрики класса.  
  
 Эти функции полезны для создания объектов, которые запрещено быть внешне с помощью [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) макрос. Они также полезны в ситуациях, где вы хотите избежать API COM, для обеспечения эффективности.  
  
 Обратите внимание, что интерфейс `Q` должен иметь связанный с ним IID, можно получить с помощью [__uuidof](../../cpp/uuidof-operator.md) оператор.  
  
### <a name="example"></a>Пример  
 В следующем примере `CDocument` созданный мастером ATL класс является производным от `CComCoClass` , реализующий **IDocument** интерфейса. Класс, зарегистрированный в карте объектов с `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO` макрос, поэтому клиенты не могут создавать экземпляры документа с помощью [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615). `CApplication` является компонентный класс, предоставляющий метод на одном из собственных интерфейсов COM для создания экземпляров класса документа. Код ниже показан как просто его для создания экземпляров класса документа с помощью `CreateInstance` член наследуется от `CComCoClass` базового класса.  
  
 [!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]  
  
##  <a name="error"></a>  CComCoClass::Error  
 Эта статическая функция настраивает `IErrorInfo` интерфейс, чтобы предоставить сведения об ошибке клиенту.  
  
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
 `lpszDesc`  
 [in] Строка, описывающая ошибку. Версия Юникода `Error` указывает, что `lpszDesc` относится к типу **LPCOLESTR**; версия ANSI указывает тип `LPCSTR`.  
  
 `iid`  
 [in] Идентификатор IID интерфейса, определение ошибки или `GUID_NULL` (значение по умолчанию), если ошибки определяется операционной системой.  
  
 `hRes`  
 [in] `HRESULT` Требуется возвращается вызывающему. Значение по умолчанию — 0. Дополнительные сведения о `hRes`, см. примечания.  
  
 `nID`  
 [in] Идентификатор ресурса, в котором хранится строка описания ошибки. Это значение должно лежать между 0x0200 до 0xFFFF, включительно. В отладочных построениях **ASSERT** Если `nID` индекса не является допустимой строкой. В сборках выпуска строка описания ошибки будет присвоено «Unknown Error».  
  
 `dwHelpID`  
 [in] Идентификатор контекста справки для ошибки.  
  
 `lpszHelpFile`  
 [in] Путь и имя файла справки, описывающее ошибку.  
  
 `hInst`  
 [in] Дескриптор для ресурса. По умолчанию этот параметр является **_AtlModule::GetResourceInstance**, где **_AtlModule** — это глобальный экземпляр [CAtlModule](../../atl/reference/catlmodule-class.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` . Дополнительные сведения см. в разделе "Заметки".  
  
### <a name="remarks"></a>Примечания  
 Для вызова `Error`, ваш объект должен реализовывать `ISupportErrorInfo Interface` интерфейса.  
  
 Если `hRes` параметр имеет ненулевое значение, затем `Error` возвращает значение `hRes`. Если `hRes` равно нулю, то первые четыре версии `Error` возвращают `DISP_E_EXCEPTION`. Две последние версии возвращают результат этого макроса **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
##  <a name="getobjectclsid"></a>  CComCoClass::GetObjectCLSID  
 Предоставляет согласованный способ получения CLSID объекта.  
  
```
static const CLSID& WINAPI GetObjectCLSID();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор класса объекта.  
  
##  <a name="getobjectdescription"></a>  CComCoClass::GetObjectDescription  
 Эта статическая функция возвращает текстовое описание для объекта класса.  
  
```
static LPCTSTR WINAPI GetObjectDescription();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Описание класса объекта.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию возвращает **NULL**. Можно переопределить этот метод с [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) макрос. Пример:  
  
 [!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]  
  
 `GetObjectDescription` вызывается методом **IComponentRegistrar::GetComponents**. **IComponentRegistrar** — это интерфейс автоматизации, дает возможность регистрировать и отменять регистрацию отдельных компонентов в библиотеке DLL. При создании объекта регистрации компонента с помощью мастера проектов ATL, мастер автоматически будет реализовывать **IComponentRegistrar** интерфейса. **IComponentRegistrar** обычно используется в Microsoft Transaction Server.  
  
 Дополнительные сведения о мастере проекта ATL см. в статье [создается проект ATL](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
