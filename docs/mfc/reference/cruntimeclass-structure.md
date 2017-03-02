---
title: "Структура CRuntimeClass | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CRuntimeClass structure
- dynamic class information
- runtime, class information
- run-time class, CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
caps.latest.revision: 20
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
ms.openlocfilehash: 17994895aec5eee3fbe67bef5f80494988906df9
ms.lasthandoff: 02/24/2017

---
# <a name="cruntimeclass-structure"></a>Структура CRuntimeClass
Каждый класс, производный от `CObject` связанные с `CRuntimeClass` структура, можно использовать для получения сведений о объекта или его базовом классе во время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CRuntimeClass  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRuntimeClass::CreateObject](#createobject)|Создает объект во время выполнения.|  
|[CRuntimeClass::FromName](#fromname)|Создает объект во время выполнения с помощью имени класса знакомы.|  
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|Определяет класс, производный от указанного класса.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|Имя класса.|  
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|Размер объекта в байтах.|  
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|Указатель на `CRuntimeClass` структуру базового класса.|  
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|Указатель на функцию, которая динамически создает объект.|  
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Возвращает `CRuntimeClass` структуры (только при динамически связан).|  
|[CRuntimeClass::m_wSchema](#m_wschema)|Номер схемы класса.|  
  
## <a name="remarks"></a>Примечания  
 `CRuntimeClass`представляет собой структуру и поэтому не имеет базового класса.  
  
 Возможность определения класса объекта во время выполнения может быть полезно, при необходимости дополнительного типа, проверяющего аргументов функции или когда необходимо написать код специального назначения, на основе класса объекта. Сведения о классе во время выполнения не поддерживается языком C++.  
  
 `CRuntimeClass`Предоставляет сведения для связанного объекта C++, такие как указатель на `CRuntimeClass` базового класса и имя класса ASCII связанного класса. Эта структура также реализует различные функции, которые могут использоваться для динамического создания объектов, указав тип объекта, используя имя и определение, если класс является производным от определенного класса.  
  
 Дополнительные сведения об использовании `CRuntimeClass`, см. в статье [сведения о классе во время выполнения доступ к](../../mfc/accessing-run-time-class-information.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CRuntimeClass`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="a-namecreateobjecta--cruntimeclasscreateobject"></a><a name="createobject"></a>CRuntimeClass::CreateObject  
 Эта функция вызывается для динамического создания класса, указанного во время выполнения.  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszClassName`  
 Знакомые имя создаваемого класса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на вновь созданный объект или **NULL** имя класса не найдена, или недостаточно памяти для создания объекта.  
  
### <a name="remarks"></a>Примечания  
 Классы, производные от `CObject` может поддерживать динамическое создание, который является возможность создания объекта указанного класса во время выполнения. Документов, представления и классы фрейма, например, должен поддерживать динамическое создание. Дополнительные сведения о динамического создания и `CreateObject` член, в разделе [CObject-класс](../../mfc/using-cobject.md) и [CObject-класс: задание уровней функциональности](../../mfc/specifying-levels-of-functionality.md).  
  
### <a name="example"></a>Пример  
  В примере показано [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="a-namefromnamea--cruntimeclassfromname"></a><a name="fromname"></a>CRuntimeClass::FromName  
 Эта функция вызывается для получения `CRuntimeClass` структуры, связанные с понятным именем.  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszClassName`  
 Знакомые имя класса, производным от `CObject`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CRuntimeClass` соответствующий имя как переданный объект `lpszClassName`. Функция возвращает **NULL** Если совпадающее имя класса не найдены.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample&17;](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="a-nameisderivedfroma--cruntimeclassisderivedfrom"></a><a name="isderivedfrom"></a>CRuntimeClass::IsDerivedFrom  
 Эта функция вызывается для определения, при вызове класс является производным от класса, указанного в *pBaseClass* параметр.  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 *pBaseClass*  
 Знакомые имя класса, производным от `CObject`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если вызов класса `IsDerivedFrom` является производным от базового класса, `CRuntimeClass` структуры, заданный как параметр; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Связь определяется «анализ» из члена класса по цепочке производных классов на самый верх. Эта функция возвращает только **FALSE** , если совпадение не найдено для базового класса.  
  
> [!NOTE]
>  Для использования `CRuntimeClass` структуры, необходимо включить `IMPLEMENT_DYNAMIC`, `IMPLEMENT_DYNCREATE`, или `IMPLEMENT_SERIAL` макрос в реализации класса, для которого требуется получить сведения о времени выполнения объекта.  
  
 Дополнительные сведения об использовании `CRuntimeClass`, см. в статье [класс CObject: сведения о классе во время выполнения доступ к](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample&18;](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="a-namemlpszclassnamea--cruntimeclassmlpszclassname"></a><a name="m_lpszclassname"></a>CRuntimeClass::m_lpszClassName  
 Завершающим нулем строка, содержащая имя класса ASCII.  
  
### <a name="remarks"></a>Примечания  
 Это имя может использоваться для создания экземпляра класса с помощью `FromName` функции-члена.  
  
### <a name="example"></a>Пример  
  В примере показано [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="a-namemnobjectsizea--cruntimeclassmnobjectsize"></a><a name="m_nobjectsize"></a>CRuntimeClass::m_nObjectSize  
 Размер объекта в байтах.  
  
### <a name="remarks"></a>Примечания  
 Если объект содержит члены данных, указывающие на выделенную память, объем памяти не включается.  
  
### <a name="example"></a>Пример  
  В примере показано [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="a-namempbaseclassa--cruntimeclassmpbaseclass"></a><a name="m_pbaseclass"></a>CRuntimeClass::m_pBaseClass  
 Если приложение статически связанной с MFC, этот элемент данных содержит указатель на `CRuntimeClass` структуру базового класса.  
  
### <a name="remarks"></a>Примечания  
 Если приложение динамически связывается с библиотекой MFC, см. раздел [m_pfnGetBaseClass](#m_pfngetbaseclass).  
  
### <a name="example"></a>Пример  
  В примере показано [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="a-namempfncreateobjecta--cruntimeclassmpfncreateobject"></a><a name="m_pfncreateobject"></a>CRuntimeClass::m_pfnCreateObject  
 Указатель на функцию конструктора по умолчанию, создающий объект класса.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель используется только если класс поддерживает динамическое создание; в противном случае, функция возвращает **NULL**.  
  
##  <a name="a-namempfngetbaseclassa--cruntimeclassmpfngetbaseclass"></a><a name="m_pfngetbaseclass"></a>CRuntimeClass::m_pfnGetBaseClass  
 Если приложение использует библиотеки MFC в общей DLL-ФАЙЛ, этот элемент данных указывает на функцию, возвращающую `CRuntimeClass` структуру базового класса.  
  
### <a name="remarks"></a>Примечания  
 Если приложение статически ссылки на библиотеки MFC, см. раздел [m_pBaseClass](#m_pbaseclass).  
  
### <a name="example"></a>Пример  
  В примере показано [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="a-namemwschemaa--cruntimeclassmwschema"></a><a name="m_wschema"></a>CRuntimeClass::m_wSchema  
 Номер схемы (-1 для классов несериализуемый).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о схеме номера в разделе [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос.  
  
### <a name="example"></a>Пример  
  В примере показано [IsDerivedFrom](#isderivedfrom).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)   
 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)   
 [RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)   
 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)   
 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)   
 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)




