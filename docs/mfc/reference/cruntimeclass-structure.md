---
title: Структура CRuntimeClass
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: 92979a10c18d9759e0ecc9f0785e56a97c0f0642
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372053"
---
# <a name="cruntimeclass-structure"></a>Структура CRuntimeClass

Каждый класс, производный от `CObject` связан с `CRuntimeClass` структура, которую можно использовать для получения сведений о объекта или его базового класса во время выполнения.

## <a name="syntax"></a>Синтаксис

```
struct CRuntimeClass
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CRuntimeClass::CreateObject](#createobject)|Создает объект во время выполнения.|
|[CRuntimeClass::FromName](#fromname)|Создает объект во время выполнения, используя имя класса знакомы.|
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|Определяет, если класс является производным от указанного класса.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|Имя класса.|
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|Размер объекта в байтах.|
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|Указатель на `CRuntimeClass` структуру базового класса.|
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|Указатель на функцию, которая динамически создает объект.|
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Возвращает `CRuntimeClass` структуры (только для доступных, когда динамически связанные).|
|[CRuntimeClass::m_wSchema](#m_wschema)|Код схемы класса.|

## <a name="remarks"></a>Примечания

`CRuntimeClass` Структура и поэтому не имеет базового класса.

Возможность определения класса объекта во время выполнения полезно в тех случаях, когда требуется дополнительного типа, проверяющего аргументов функции или когда необходимо написать специальный код, на основе класса объекта. Сведения о классе среды выполнения не поддерживается языком C++.

`CRuntimeClass` Предоставляет сведения о связанного объекта C++, такие как указатель на `CRuntimeClass` базового класса и имя класса ASCII связанного класса. Эта структура также реализует различные функции, которые могут использоваться для динамического создания объектов, указав тип объекта, используя привычным именем и определение, если связанный класс является производным от определенного класса.

Дополнительные сведения об использовании `CRuntimeClass`, см. в статье [доступ к сведениям о классе среды выполнения](../../mfc/accessing-run-time-class-information.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CRuntimeClass`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="createobject"></a>  CRuntimeClass::CreateObject

Вызывайте эту функцию, чтобы динамически создать указанный класс во время выполнения.

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
Знакомые имя создаваемого класса.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданный объект или значение NULL, если имя класса не найден, или недостаточно памяти для создания объекта.

### <a name="remarks"></a>Примечания

Классы, производные от `CObject` может поддерживать динамическое создание, который является возможность создания объекта указанного класса во время выполнения. Документ, представления и классы фрейма, к примеру, должен поддерживать динамическое создание. Дополнительные сведения о динамическое создание и `CreateObject` член, см. в разделе [класс CObject](../../mfc/using-cobject.md) и [класс CObject: Задание уровней функциональности](../../mfc/specifying-levels-of-functionality.md).

### <a name="example"></a>Пример

  См. в примере [IsDerivedFrom](#isderivedfrom).

##  <a name="fromname"></a>  CRuntimeClass::FromName

Вызывайте эту функцию для получения `CRuntimeClass` структуры, связанные с привычным именем.

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>Параметры

*lpszClassName*<br/>
Знакомые имя класса, производным от `CObject`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CRuntimeClass` объект, соответствующий имени при передаче в *lpszClassName*. Функция возвращает NULL, если найдено совпадающее имя класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

##  <a name="isderivedfrom"></a>  CRuntimeClass::IsDerivedFrom

Вызывайте эту функцию, чтобы определить, если вызывающий класс является производным от класса, указанного в *pBaseClass* параметра.

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>Параметры

*pBaseClass*<br/>
Знакомые имя класса, производным от `CObject`.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если класс вызывающего `IsDerivedFrom` является производным от базового класса, `CRuntimeClass` структуры, заданного в качестве параметра; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Связь определяется «обход» из члена класса вверх по цепочке производных классов вплоть до верхней. Эта функция возвращает значение FALSE только в том случае, если совпадений не найдено для базового класса.

> [!NOTE]
>  Чтобы использовать `CRuntimeClass` структуры, необходимо включить макрос IMPLEMENT_DYNAMIC, IMPLEMENT_DYNCREATE или IMPLEMENT_SERIAL в реализации класса, для которого требуется получить сведения о времени выполнения объекта.

Дополнительные сведения об использовании `CRuntimeClass`, см. в статье [класс CObject: Доступ к сведениям о классе среды выполнения](../../mfc/accessing-run-time-class-information.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

##  <a name="m_lpszclassname"></a>  CRuntimeClass::m_lpszClassName

Завершающаяся нулем строка, содержащая имя класса ASCII.

### <a name="remarks"></a>Примечания

Это имя может использоваться для создания экземпляра класса с использованием `FromName` функция-член.

### <a name="example"></a>Пример

  См. в примере [IsDerivedFrom](#isderivedfrom).

##  <a name="m_nobjectsize"></a>  CRuntimeClass::m_nObjectSize

Размер объекта, в байтах.

### <a name="remarks"></a>Примечания

Если объект имеет данные-члены, указывающими на выделенную память, объем памяти не включается.

### <a name="example"></a>Пример

  См. в примере [IsDerivedFrom](#isderivedfrom).

##  <a name="m_pbaseclass"></a>  CRuntimeClass::m_pBaseClass

Если приложение статически скомпонованную с MFC, этот элемент данных содержит указатель на `CRuntimeClass` структуру базового класса.

### <a name="remarks"></a>Примечания

Если приложение динамически скомпонована с MFC библиотеки, см. в разделе [m_pfnGetBaseClass](#m_pfngetbaseclass).

### <a name="example"></a>Пример

  См. в примере [IsDerivedFrom](#isderivedfrom).

##  <a name="m_pfncreateobject"></a>  CRuntimeClass::m_pfnCreateObject

Указатель на функцию в конструктор по умолчанию, который создает объект класса.

### <a name="remarks"></a>Примечания

Этот указатель допустим, только если класс поддерживает динамическое создание; в противном случае функция возвращает значение NULL.

##  <a name="m_pfngetbaseclass"></a>  CRuntimeClass::m_pfnGetBaseClass

Если приложение использует библиотеку MFC в общей DLL-ФАЙЛ, этот элемент данных будет указывать на функцию, возвращающую `CRuntimeClass` структуру базового класса.

### <a name="remarks"></a>Примечания

Если приложение выполняется статическая привязка библиотеки MFC, см. в разделе [m_pBaseClass](#m_pbaseclass).

### <a name="example"></a>Пример

  См. в примере [IsDerivedFrom](#isderivedfrom).

##  <a name="m_wschema"></a>  CRuntimeClass::m_wSchema

Код схемы (-1 для классов несериализуемый).

### <a name="remarks"></a>Примечания

Дополнительные сведения о схеме номера, см. в разделе [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос.

### <a name="example"></a>Пример

  См. в примере [IsDerivedFrom](#isderivedfrom).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
