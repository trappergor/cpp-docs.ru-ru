---
title: "Структура CRuntimeClass | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CRuntimeClass
dev_langs: C++
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: db4820fa1496bbedebba8392ab0947cfafdf03e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cruntimeclass-structure"></a>Структура CRuntimeClass
Каждый класс, производный от `CObject` связан с `CRuntimeClass` структуру, можно использовать для получения сведений о объекта или его базовый класс во время выполнения.  
  
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
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|Определяет, если данный класс является производным от указанного класса.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|Имя класса.|  
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|Размер объекта в байтах.|  
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|Указатель на `CRuntimeClass` структура базового класса.|  
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|Указатель на функцию, которая динамически создает объект.|  
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Возвращает `CRuntimeClass` структуры (только при динамически связанные).|  
|[CRuntimeClass::m_wSchema](#m_wschema)|Число класса схемы.|  
  
## <a name="remarks"></a>Примечания  
 `CRuntimeClass`Структура и поэтому не имеет базового класса.  
  
 Возможность определения класса объекта во время выполнения может быть полезно при необходимости дополнительного типа, проверяющего аргументов функции, или когда необходимо написать код специального назначения, на основе класса объекта. Сведения о классе во время выполнения не поддерживается языком C++.  
  
 `CRuntimeClass`Предоставляет сведения о связанного объекта C++, такие как указатель на `CRuntimeClass` базового класса и имя класса ASCII связанного класса. Эта структура также включает различные функции, которые могут использоваться для динамического создания объектов, указав тип объекта, используя знакомые имя и определение, если класс является производным от определенного класса.  
  
 Дополнительные сведения об использовании `CRuntimeClass`, см. в статье [доступ к сведениям о классе во время выполнения](../../mfc/accessing-run-time-class-information.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CRuntimeClass`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="createobject"></a>CRuntimeClass::CreateObject  
 Эта функция вызывается для динамического создания заданного класса во время выполнения.  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszClassName`  
 Имя класса, чтобы создать знакомы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на вновь созданный объект или **NULL** Если имя класса не найдено или не хватает памяти для создания объекта.  
  
### <a name="remarks"></a>Примечания  
 Классы, производные от `CObject` может поддерживать динамическое создание, то есть возможности для создания объекта указанного класса во время выполнения. Документ, представление и классы фрейма, например, должен поддерживать динамическое создание. Дополнительные сведения о динамическое создание и `CreateObject` член, в разделе [CObject-класс](../../mfc/using-cobject.md) и [класс CObject: задание уровней функциональности](../../mfc/specifying-levels-of-functionality.md).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="fromname"></a>CRuntimeClass::FromName  
 Эта функция вызывается для получения `CRuntimeClass` структур, связанных с понятным именем.  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszClassName`  
 Знакомые имя класса, производным от `CObject`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CRuntimeClass` объект, соответствующий имени как передано `lpszClassName`. Функция возвращает **NULL** найденные соответствующее имя класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="isderivedfrom"></a>CRuntimeClass::IsDerivedFrom  
 Эта функция вызывается для определения, если вызывающий класс является производным от класса, указанного в *pBaseClass* параметра.  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 *pBaseClass*  
 Знакомые имя класса, производным от `CObject`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если вызов класса `IsDerivedFrom` является производным от базового класса, `CRuntimeClass` структуры, заданного в качестве параметра; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Связь определяется «обход» из класса элемента вверх по цепочке производных классов, вплоть до верхней. Эта функция возвращает только **FALSE** , если совпадение не найдено для базового класса.  
  
> [!NOTE]
>  Для использования `CRuntimeClass` структуры, необходимо включить `IMPLEMENT_DYNAMIC`, `IMPLEMENT_DYNCREATE`, или `IMPLEMENT_SERIAL` макрос в реализации класса, для которого требуется получить сведения о времени выполнения объекта.  
  
 Дополнительные сведения об использовании `CRuntimeClass`, см. в статье [класс CObject: доступ к сведениям о классе во время выполнения](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="m_lpszclassname"></a>CRuntimeClass::m_lpszClassName  
 Нулем строка, содержащая имя класса ASCII.  
  
### <a name="remarks"></a>Примечания  
 Это имя может использоваться для создания экземпляра класса с помощью `FromName` функции-члена.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_nobjectsize"></a>CRuntimeClass::m_nObjectSize  
 Размер объекта в байтах.  
  
### <a name="remarks"></a>Примечания  
 Если объект имеет члены данных этой точки выделенную память, объем памяти, не включается.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pbaseclass"></a>CRuntimeClass::m_pBaseClass  
 Если приложение статически связывается с MFC, этот элемент данных содержит указатель на `CRuntimeClass` структура базового класса.  
  
### <a name="remarks"></a>Примечания  
 Если приложение динамически привязано к библиотеке MFC, см. раздел [m_pfnGetBaseClass](#m_pfngetbaseclass).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pfncreateobject"></a>CRuntimeClass::m_pfnCreateObject  
 Указатель на функцию в конструктор по умолчанию, которая создает объект класса.  
  
### <a name="remarks"></a>Примечания  
 Этот указатель допустимо, только если класс поддерживает динамическое создание; в противном случае функция возвращает **NULL**.  
  
##  <a name="m_pfngetbaseclass"></a>CRuntimeClass::m_pfnGetBaseClass  
 Если приложение использует библиотеку MFC в общей библиотеке DLL, этот элемент данных указывает на функцию, возвращающую `CRuntimeClass` структура базового класса.  
  
### <a name="remarks"></a>Примечания  
 Если приложение статически связывается с библиотеки MFC, см. раздел [m_pBaseClass](#m_pbaseclass).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_wschema"></a>CRuntimeClass::m_wSchema  
 Номер схемы (-1 для классов несериализуемый).  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о схеме номера см. в разделе [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [IsDerivedFrom](#isderivedfrom).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)   
 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)   
 [RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)   
 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)   
 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)   
 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)



