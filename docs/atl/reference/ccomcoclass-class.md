---
title: "Класс CComCoClass | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6201051a38ac65788086dcf7ee4c3f3441988e71
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcoclass-class"></a>Класс CComCoClass
Этот класс предоставляет методы для создания экземпляров класса и получения его свойств.  
  
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
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCoClass::CreateInstance](#createinstance)|(Статический) Создает экземпляр класса и запросы для интерфейса.|  
|[CComCoClass::Error](#error)|(Статический) Возвращает сведения об ошибке клиенту.|  
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(Статический) Возвращает идентификатор класса объекта.|  
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(Статический) Переопределите для возврата описание объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CComCoClass`Предоставляет методы для получения идентификатора CLSID объекта, параметр сведений об ошибках и создания экземпляров класса. Любой класс, зарегистрирован в [карту объектов](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f) должен быть производным от `CComCoClass`.  
  
 `CComCoClass`также определяет модель по умолчанию класса фабрики и статистической обработки для объекта. `CComCoClass`использует следующие два макроса:  
  
- [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4) объявляет фабрики классов для [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).  
  
- [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab) объявляет, что объект может быть агрегатом.  
  
 Любой из этих умолчаний можно переопределить, указав другой макрос в определении класса. Например, чтобы использовать [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) вместо `CComClassFactory`, укажите [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285) макрос:  
  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="createinstance"></a>CComCoClass::CreateInstance  
 Используйте эти `CreateInstance` функции для создания экземпляра COM объекта и получить указатель на интерфейс без использования COM API.  
  
```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `Q`  
 COM-интерфейса, которое должно возвращаться через `pp`.  
  
 *punkOuter*  
 [in] Внешняя Неизвестная или управление неизвестно агрегатной функции.  
  
 `pp`  
 [out] Адрес переменной указателя, получающей указатель запрошенный интерфейс, если после успешного создания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` . В разделе [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] описание возможных возвращаемых значений.  
  
### <a name="remarks"></a>Примечания  
 Использовать первую перегрузку этой функции для создания типичных объекта; Используйте вторую перегрузку, когда необходимо объединить с создаваемым объектом.  
  
 ATL-класс, реализующий необходимые COM-объект (то есть класс, используемый как первый параметр шаблона [CComCoClass](../../atl/reference/ccomcoclass-class.md)) должен находиться в том же проекте, что и вызывающий код. Создание COM-объекта будет проведена, зарегистрированные для этого класса ATL фабрики класса.  
  
 Эти функции полезны для создания объектов, которые запрещено, создаваемыми извне с помощью [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](http://msdn.microsoft.com/library/abdc093c-6502-42de-8419-b7ebf45299d1) макрос. Они также полезны в ситуациях, где вы хотите избежать API COM, из соображений эффективности.  
  
 Обратите внимание, что интерфейс `Q` должен иметь связанные с ним IID, могут быть получены с помощью [__uuidof](../../cpp/uuidof-operator.md) оператор.  
  
### <a name="example"></a>Пример  
 В следующем примере `CDocument` созданный мастером ATL класс является производным от `CComCoClass` , реализующий **IDocument** интерфейса. Класс регистрируется в карте объектов с `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO` макрос, поэтому клиенты не могут создавать экземпляры документов с помощью [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615). `CApplication`является компонентный класс, предоставляющий метод на один из собственных интерфейсов COM для создания экземпляров класса документа. Кода ниже показан как просто создать экземпляры класса документа с помощью `CreateInstance` член наследуется от `CComCoClass` базового класса.  
  
 [!code-cpp[NVC_ATL_COM&#11;](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]  
  
##  <a name="error"></a>CComCoClass::Error  
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
 [in] Строка, описывающая ошибку. Версия Юникода `Error` указывает, что `lpszDesc` типа **LPCOLESTR**; тип в формате ANSI `LPCSTR`.  
  
 `iid`  
 [in] Идентификатор IID интерфейса, определение ошибки или `GUID_NULL` (значение по умолчанию), если ошибки определяется операционной системой.  
  
 `hRes`  
 [in] `HRESULT` Требуется возвращается вызывающему. Значение по умолчанию — 0. Дополнительные сведения о `hRes`, см.  
  
 `nID`  
 [in] Идентификатор ресурса, где хранится строка описания ошибки. Это значение должно находиться между 0x0200 и 0xFFFF включительно. В отладочных построениях **ASSERT** Если это приведет к `nID` индекса не является допустимой строкой. В сборке выпуска строку описания ошибки будет присвоено «Неизвестная ошибка».  
  
 `dwHelpID`  
 [in] Идентификатор контекста справки для ошибки.  
  
 `lpszHelpFile`  
 [in] Путь и имя файла справки, описывающий ошибку.  
  
 `hInst`  
 [in] Дескриптор для ресурса. По умолчанию этот параметр является **_AtlModule::GetResourceInstance**, где **_AtlModule** — глобальный экземпляр [CAtlModule](../../atl/reference/catlmodule-class.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` . Дополнительные сведения см. в разделе "Заметки".  
  
### <a name="remarks"></a>Примечания  
 Для вызова `Error`, объект должен реализовать `ISupportErrorInfo Interface` интерфейса.  
  
 Если `hRes` параметр имеет ненулевое значение, затем `Error` возвращает значение `hRes`. Если `hRes` равно нулю, то первые четыре версии `Error` вернуть `DISP_E_EXCEPTION`. Последние две версии возвращают результат макрос **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
##  <a name="getobjectclsid"></a>CComCoClass::GetObjectCLSID  
 Предоставляет согласованный способ получения CLSID объекта.  
  
```
static const CLSID& WINAPI GetObjectCLSID();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор класса объекта.  
  
##  <a name="getobjectdescription"></a>CComCoClass::GetObjectDescription  
 Эта статическая функция возвращает текстовое описание класса объекта.  
  
```
static LPCTSTR WINAPI GetObjectDescription();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Описание класса объекта.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию возвращает **NULL**. Можно переопределить этот метод с [DECLARE_OBJECT_DESCRIPTION](http://msdn.microsoft.com/library/32ac881c-97b1-44e2-a017-0e23eb99ac93) макрос. Пример:  
  
 [!code-cpp[NVC_ATL_COM&#12;](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]  
  
 `GetObjectDescription`вызывается методом **IComponentRegistrar::GetComponents**. **IComponentRegistrar** интерфейс автоматизации позволяет регистрировать и отменять регистрацию отдельных компонентов в библиотеке DLL. При создании объекта регистрации компонента с помощью мастера проектов ATL, мастер автоматически будет реализовать **IComponentRegistrar** интерфейса. **IComponentRegistrar** обычно используется в Microsoft Transaction Server.  
  
 Дополнительные сведения о мастере проекта ATL см. в статье [создается проект ATL](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

