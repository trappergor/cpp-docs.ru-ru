---
title: 'TN039: Реализация автоматизации MFC-OLE | Документация Майкрософт'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59eca912aab816f75ce8d585036f8f900c4f7bd3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399883"
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039. Реализация автоматизации MFC/OLE

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

## <a name="overview-of-ole-idispatch-interface"></a>Обзор интерфейса IDispatch OLE

`IDispatch` Интерфейс является средством, по которому приложений предоставляют методы и свойства, такие, которые другие приложения, например Visual BASIC или других языках, могут сделать использование функций приложения. Самая важная часть этого интерфейса — `IDispatch::Invoke` функции. MFC использует «схемы подготовки к отправке» для реализации `IDispatch::Invoke`. Схема подготовки к отправке предоставляет сведения о реализации MFC на макет или «формы» вашего `CCmdTarget`-производные классы, таким образом, что она может напрямую управлять свойствами объекта, или вызов функций в пределах объекта таким образом, чтобы удовлетворить-членов `IDispatch::Invoke` запросы.

В большинстве случаев ClassWizard MFC взаимодействие и для скрытия большинства различными аспектами OLE-автоматизации из прикладному программисту. Программист сосредоточен на фактический функциональные возможности для предоставления в приложении и не нужно беспокоиться о остальную.

Бывают случаи, тем не менее, где это необходимо понять, что MFC делает за кулисами. Эта заметка будет решить, как назначается **DISPID**s для функций-членов и свойств. Знаний об алгоритме, MFC использует для назначения **DISPID**s необходимо только в том случае, если вам нужно знать идентификаторы, например при создании «библиотеку типов» для объектов приложения.

## <a name="mfc-dispid-assignment"></a>Назначение MFC DISPID

Несмотря на то, что автоматизации (Visual Basic пользователя, например), конечный пользователь видит фактические имена автоматизации включены свойства и методы в своем коде (например, obj. ShowWindow), реализация `IDispatch::Invoke` не получать фактические имена. В целях оптимизации оно получает **DISPID**, который является 32-разрядных magic куки-файл», описывающий метод или свойство, к которому осуществляет доступ. Эти **DISPID** значения возвращаются из `IDispatch` реализации через другой метод с именем `IDispatch::GetIDsOfNames`. Приложение клиента автоматизации вызовет `GetIDsOfNames` после для каждого члена или свойство он намеревается доступ и их кэширование для ее последующих вызовов `IDispatch::Invoke`. Таким образом, поиск ресурсоемкие строки выполняется только один раз за использование объекта вместо один раз за `IDispatch::Invoke` вызова.

Определяет MFC **DISPID**для каждого метода и свойства, основываясь на две вещи:

- Расстояние от верха диспетчерскую карту (1 относительно)

- Расстояние от диспетчерскую карту из наиболее производного класса (0 относительный)

**DISPID** делится на две части. **LOWORD** из **DISPID** содержит первый компонент, расстояние от верха диспетчерскую карту. **HIWORD** содержит расстояние от наиболее производный класс. Пример:

```cpp
class CDispPoint : public CCmdTarget
{
public:
    short m_x, m_y;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

class CDisp3DPoint : public CDispPoint
{
public:
    short m_z;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)
END_DISPATCH_MAP()

BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
END_DISPATCH_MAP()
```

Как вы видите, существует два класса, которые предоставляют интерфейсы автоматизации OLE. Один из этих классов является производным от другого и таким образом использует функции базового класса, включая части автоматизации OLE («x» и «y» свойства в данном случае).

MFC создаст **DISPID**s для класса CDispPoint следующим образом:

```cpp
property X    (DISPID)0x00000001
property Y    (DISPID)0x00000002
```

Так как в базовом классе, не имеют свойств **HIWORD** из **DISPID** всегда равно нулю (расстояние от наиболее производный класс для CDispPoint равно нулю).

MFC создаст **DISPID**s для класса CDisp3DPoint следующим образом:

```cpp
property Z    (DISPID)0x00000001
property X    (DISPID)0x00010001
property Y    (DISPID)0x00010002
```

Получает свойства Z **DISPID** с нуля **HIWORD** так, как он определен в классе, который предоставляет свойства, CDisp3DPoint. Поскольку свойства X и Y определяются в базовом классе, **HIWORD** из **DISPID** имеет значение 1, так как класс, в котором определены эти свойства находится на расстоянии одной наследования наиболее производный класс.

> [!NOTE]
> **LOWORD** всегда определяется по позиции в схеме, даже если существуют записи в схеме с явной **DISPID** (см. в разделе следующего раздела приведены сведения на **_ID** версии `DISP_PROPERTY` и `DISP_FUNCTION` макросов).

## <a name="advanced-mfc-dispatch-map-features"></a>Дополнительные функции карты диспетчеризации MFC

Существует ряд дополнительных функций, которые ClassWizard не поддерживаются в этом выпуске Visual C++. Поддерживает ClassWizard `DISP_FUNCTION`, `DISP_PROPERTY`, и `DISP_PROPERTY_EX` которые определяют метод, свойство переменной члена и член функций get и set свойств, соответственно. Обычно эти возможности являются все, что требуется для создания большинства серверов автоматизации.

Следующие дополнительные макросы можно использовать при ClassWizard поддерживаются макросы не соответствуют потребностям: `DISP_PROPERTY_NOTIFY`, и `DISP_PROPERTY_PARAM`.

## <a name="disppropertynotify--macro-description"></a>DISP_PROPERTY_NOTIFY — Описание макроса

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    pszName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*pszName*<br/>
Внешнее имя свойства.

*Имя пользователя*<br/>
Имя переменной-члена, в котором хранится свойство.

*pfnAfterSet*<br/>
Имя функции-члена для вызова при изменении свойства.

*vtPropType*<br/>
Значение, указывающее тип свойства.

### <a name="remarks"></a>Примечания

Этот макрос очень напоминает DISP_PROPERTY, за исключением того, что он принимает дополнительный аргумент. Дополнительный аргумент, *pfnAfterSet,* должно быть функцией-членом, не возвращает ничего и не принимает никаких параметров «void OnPropertyNotify()». Он будет вызываться **после** переменную-член был изменен.

## <a name="disppropertyparam--macro-description"></a>DISP_PROPERTY_PARAM — Описание макроса

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*pszName*<br/>
Внешнее имя свойства.

*memberGet*<br/>
Имя функции-члена, используемый для получения свойства.

*набор элементов*<br/>
Имя функции-члена, используемый для задания свойства.

*vtPropType*<br/>
Значение, указывающее тип свойства.

*vtsParams*<br/>
Строка пространства запятыми VTS_ для каждого параметра.

### <a name="remarks"></a>Примечания

Во многом подобно disp_property_ex-макрос, этот макрос определяет свойство для доступа к отдельной функции-члены Get и Set. Этот макрос, тем не менее, можно указать список параметров для свойства. Это полезно для реализации свойства, которые индексируются или параметризованные иным способом. Параметры всегда помещаются во-первых, следуют новое значение для свойства. Пример:

```cpp
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH, VTS_I2 VTS_I2)
```

будет соответствовать для получения и задания функции-члены:

```cpp
LPDISPATCH CMyObject::GetItem(short row, short col)
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)
```

## <a name="dispxxxxid--macro-descriptions"></a>DISP_XXXX_ID — Описания макросов

```cpp
DISP_FUNCTION_ID(
    theClass,
    pszName,
    dispid,
    pfnMember,
    vtRetVal,
    vtsParams)
DISP_PROPERTY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    vtPropType)
DISP_PROPERTY_NOTIFY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    pfnAfterSet,
    vtPropType)
DISP_PROPERTY_EX_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType)
DISP_PROPERTY_PARAM_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*pszName*<br/>
Внешнее имя свойства.

*Идентификатор DISPID*<br/>
Фиксированный идентификатор DISPID для свойства или метода.

*pfnGet*<br/>
Имя функции-члена, используемый для получения свойства.

*pfnSet*<br/>
Имя функции-члена, используемый для задания свойства.

*Имя пользователя*<br/>
Имя переменной-члена для сопоставления свойства

*vtPropType*<br/>
Значение, указывающее тип свойства.

*vtsParams*<br/>
Строка пространства запятыми VTS_ для каждого параметра.

### <a name="remarks"></a>Примечания

Эти макросы позволяют пользователю указать **DISPID** фиксированного MFC автоматически назначить один. Эти дополнительные макросов имеют те же имена, за исключением того, этот идентификатор добавляется к имени макроса (например **DISP_PROPERTY_ID**) и идентификатор зависит от параметра, сразу после заданного *pszName* параметра. См. в разделе AFXDISP. H Дополнительные сведения о этих макросов. **_ID** записи должны располагаться в конце диспетчерскую карту. Они будут применяться автоматическое **DISPID** поколение так же, как отличный от **_ID** версии макроса будет ( **DISPID**s определяются по позиции). Пример:

```cpp
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)
END_DISPATCH_MAP()
```

MFC создает идентификаторы DISPID для класса CDisp3DPoint следующим образом:

```cpp
property X    (DISPID)0x00020003
property Y    (DISPID)0x00000002
property Z    (DISPID)0x00000001
```

Указав фиксированный **DISPID** полезен для обеспечения обратной совместимости для ранее существующего интерфейса диспетчеризации, а также реализовать определенные системы и определены методы или свойства (как правило, определяется отрицательное  **Идентификатор DISPID**, такие как **DISPID_NEWENUM** коллекции).

## <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>Извлечение интерфейса IDispatch для COleClientItem

Многие серверы будут поддерживать автоматизации в рамках своих объектов документа, а также возможности сервера OLE. Чтобы получить доступ к этому интерфейсу автоматизации, это необходимо для прямой доступ к `COleClientItem::m_lpObject` переменной-члена. В приведенном ниже коде извлечет `IDispatch` интерфейс для объекта, производного от `COleClientItem`. Приведенный ниже код можно включить в приложение, если найти эту функцию необходимо:

```cpp
LPDISPATCH CMyClientItem::GetIDispatch()
{
    ASSERT_VALID(this);
    ASSERT(m_lpObject != NULL);

    LPUNKNOWN lpUnk = m_lpObject;

    Run();      // must be running

    LPOLELINK lpOleLink = NULL;
    if (m_lpObject->QueryInterface(IID_IOleLink,
        (LPVOID FAR*)&lpOleLink) == NOERROR)
    {
        ASSERT(lpOleLink != NULL);
        lpUnk = NULL;
        if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)
        {
            TRACE0("Warning: Link is not connected!\n");
            lpOleLink->Release();
            return NULL;
        }
        ASSERT(lpUnk != NULL);
    }

    LPDISPATCH lpDispatch = NULL;
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch) != NOERROR)
    {
        TRACE0("Warning: does not support IDispatch!\n");
        return NULL;
    }

    ASSERT(lpDispatch != NULL);
    return lpDispatch;
}
```

Возвращаемый интерфейс диспетчеризации затем можно непосредственно использовать или подключенных к этой функции `COleDispatchDriver` для доступа к строго типизированным. Если использовать напрямую, убедитесь, что вызывать его `Release` член когда через указатель ( `COleDispatchDriver` деструктор достигается путем по умолчанию).

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
