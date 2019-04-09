---
title: Класс CMenuTearOffManager
ms.date: 10/18/2018
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
ms.openlocfilehash: 8b92ddad9d3a6de41cf6914dee268f6e54b5d420
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776067"
---
# <a name="cmenutearoffmanager-class"></a>Класс CMenuTearOffManager

Управление перемещаемыми меню. Перемещаемое меню — это меню в строке меню. Пользователь может удалить перемещаемое меню из строки меню, превращая перемещаемое меню в плавающее.

   Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|Создает объект `CMenuTearOffManager`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMenuTearOffManager::Build](#build)||
|[CMenuTearOffManager::GetRegPath](#getregpath)||
|[CMenuTearOffManager::Initialize](#initialize)|Инициализирует `CMenuTearOffManager` объекта.|
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||
|[CMenuTearOffManager::Parse](#parse)||
|[CMenuTearOffManager::Reset](#reset)||
|[CMenuTearOffManager::SetInUse](#setinuse)||
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||

## <a name="remarks"></a>Примечания

Чтобы использовать перемещаемые меню в приложении, необходимо иметь `CMenuTearOffManager` объекта. В большинстве случаев не создать или инициализировать `CMenuTearOffManager` объекта напрямую. Это осуществляется автоматически при вызове [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus) функции.

## <a name="example"></a>Пример

В следующем примере показано, как для создания и инициализации `CMenuTearOffManager` путем вызова метода `CWinAppEX::EnableTearOffMenus` метод. Этот фрагмент кода входит в состав [примера Word Pad](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxmenutearoffmanager.h

##  <a name="build"></a>  CMenuTearOffManager::Build

```
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>Параметры

[in] *uiTearOffBarID*<br/>

[in] *strText*<br/>

### <a name="remarks"></a>Примечания

##  <a name="cmenutearoffmanager"></a>  CMenuTearOffManager::CMenuTearOffManager

Создает [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) объекта.

```
CMenuTearOffManager();
```

### <a name="remarks"></a>Примечания

В большинстве случаев не следует создавать `CMenuTearOffManager` вручную. Платформа приложения создает `CMenuTearOffManager` объекта при вызове [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus).

##  <a name="getregpath"></a>  CMenuTearOffManager::GetRegPath

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="initialize"></a>  CMenuTearOffManager::Initialize

Инициализирует [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md) объекта.

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>Параметры

*lpszRegEntry*<br/>
[in] Строка, содержащая путь к записи реестра. Приложений сохраняет параметры для перемещаемой панелей в этой записи реестра.

*uiTearOffMenuFirst*<br/>
[in] Первый идентификатор меню перемещаемое меню.

*uiTearOffMenuLast*<br/>
[in] Идентификатор последнего меню для перемещаемое меню.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Диапазон идентификаторов, меню из *uiTearOffMenuFirst* для *uiTearOffMenuLast* должен быть непрерывный интервал. Интервал определяет количество перемещаемые меню, которые могут присутствовать в то же время, в приложении.

##  <a name="isdynamicid"></a>  CMenuTearOffManager::IsDynamicID

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>Параметры

[in] *uiID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="parse"></a>  CMenuTearOffManager::Parse

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>Параметры

[in] *str*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="reset"></a>  CMenuTearOffManager::Reset

```
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>Параметры

[in] *hmenu*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setinuse"></a>  CMenuTearOffManager::SetInUse

```
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>Параметры

[in] *uiCmdId*<br/>

[in] *bUse*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setuptearoffmenus"></a>  CMenuTearOffManager::SetupTearOffMenus

```
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

[in] *hMenu*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
