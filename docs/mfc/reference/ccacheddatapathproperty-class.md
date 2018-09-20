---
title: Класс CCachedDataPathProperty | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c22d905e50c6811c82ee54d6ec08c57ef3f41182
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382834"
---
# <a name="ccacheddatapathproperty-class"></a>Класс CCachedDataPathProperty

Реализует свойство элемента управления OLE, асинхронно переданного и кэшированного в файле памяти.

## <a name="syntax"></a>Синтаксис

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Создает объект `CCachedDataPathProperty`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile` Объект, в котором для кэширования данных.|

## <a name="remarks"></a>Примечания

Файл памяти сохраняются в оперативной памяти, а не на диске и используется для передачи, чем обеспечивается быстродействие временного.

Вместе с `CAysncMonikerFile` и `CDataPathProperty`, `CCachedDataPathProperty` предоставляет функциональные возможности для использования асинхронных моникеров в элементах управления OLE. С помощью `CCachedDataPathProperty` объектов, можно асинхронно передавать данные из источника URL-адрес или файл и сохраните его в памяти файл с помощью `m_Cache` общей переменной. Все данные хранятся в файле памяти, и нет необходимости в Переопределите [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) только если вы хотите отслеживать уведомления и отвечать. Например, если вы передаете большой. GIF-файл и хотите уведомить элемент управления, что получены дополнительные данные, и он должен выполнить перерисовку, переопределить `OnDataAvailable` на уведомление.

Класс `CCachedDataPathProperty` является производным от `CDataPathProperty`.

Дополнительные сведения о способах использования асинхронных моникеров и элементы управления ActiveX в веб-приложений см. в разделах:

- [Интернете первые шаги: Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)

- [Интернете первые шаги: Асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

##  <a name="ccacheddatapathproperty"></a>  CCachedDataPathProperty::CCachedDataPathProperty

Создает объект `CCachedDataPathProperty`.

```
CCachedDataPathProperty(COleControl* pControl = NULL);


CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>Параметры

*pControl*<br/>
Указатель на объект элемента управления ActiveX, связываемое с этим `CCachedDataPathProperty` объекта.

*lpszPath*<br/>
Путь, который может быть абсолютным или относительным, используется для создания асинхронного моникера, который ссылается на фактическое расположение абсолютный свойства. `CCachedDataPathProperty` использует URL-адреса, не имена файлов. Если вы хотите, чтобы `CCachedDataPathProperty` объекта для файла, начале file:// к пути.

### <a name="remarks"></a>Примечания

`COleControl` Объекта, на который указывает *pControl* используется [откройте](../../mfc/reference/cdatapathproperty-class.md#open) и получить производными классами. Если *pControl* имеет значение NULL, элемент управления, используемый с `Open` следует задавать с [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Если *lpszPath* имеет значение NULL, можно передать путь через `Open` или установка его с помощью [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).

##  <a name="m_cache"></a>  CCachedDataPathProperty::m_Cache

Содержит имя класса в файл памяти, в который кэшируются данные.

```
CMemFile m_Cache;
```

### <a name="remarks"></a>Примечания

Файл памяти хранятся в оперативной памяти, а не на диске.

## <a name="see-also"></a>См. также

[Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)
