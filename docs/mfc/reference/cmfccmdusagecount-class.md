---
title: Класс CMFCCmdUsageCount
ms.date: 11/04/2016
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
ms.openlocfilehash: b4ad9a60831feb6fa1147ea3f8bcfd5c6badd06c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275367"
---
# <a name="cmfccmdusagecount-class"></a>Класс CMFCCmdUsageCount

Отслеживает загруженность сообщений Windows, например когда пользователь выбирает элемент меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание:|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Конструктор по умолчанию.|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание:|
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Увеличивает на единицу счетчик, который связан с заданной команде.|
|[CMFCCmdUsageCount::GetCount](#getcount)|Получает счетчик использования, который сопоставлен заданному идентификатору команды.|
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Определяет, собираются ли этот объект минимальный объем данных отслеживания.|
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Определяет, используется ли часто заданную команду.|
|[CMFCCmdUsageCount::Reset](#reset)|Удаляет счетчик использования всех команд.|
|[CMFCCmdUsageCount::Serialize](#serialize)|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Общие наборы значений `CMFCCmdUsageCount` данные-члены класса.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|name|Описание:|
|`m_CmdUsage`|Объект `CMap` объект, который сопоставляет команды их счетчики использования.|
|`m_nMinUsagePercentage`|Процент минимального срока использования команды часто использоваться.|
|`m_nStartCount`|Счетчик начала, который используется для определения того, собираются ли этот объект минимальный объем данных отслеживания.|
|`m_nTotalUsage`|Количество всех отслеживаемых команд.|

### <a name="remarks"></a>Примечания

`CMFCCmdUsageCount` Класс сопоставляется каждый числовой идентификатор сообщения Windows счетчика 32-разрядного целого числа без знака. `CMFCToolBar` Этот класс используется для отображения панели инструментов, часто используемые элементы. Дополнительные сведения о `CMFCToolBar`, см. в разделе [класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).

Можно сохранить `CMFCCmdUsageCount` класса данных между запусками программы. Используйте [CMFCCmdUsageCount::Serialize](#serialize) метод сериализации данных члена класса и [CMFCCmdUsageCount::SetOptions](#setoptions) метод для задания общего члена данных.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcmdusagecount.h

##  <a name="addcmd"></a>  CMFCCmdUsageCount::AddCmd

Увеличивает на единицу счетчик, который связан с заданной команде.

```
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание:|
|*uiCmd*|[in] Указывает команду счетчик будет изменяться.|

### <a name="remarks"></a>Примечания

Этот метод добавляет новую запись к структуре карты счетчиков команда `m_CmdUsage`, если запись еще не существует.

Этот метод не выполняет никаких действий в следующих случаях:

- Платформа панель инструментов находится в режиме настройки ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) метод возвращает ненулевое значение).

- Команда ссылается на разделитель меню или подменю ( *uiCmd* равно 0 или -1).

- *uiCmd* ссылается на стандартную команду (глобальный `IsStandardCommand` функция возвращает ненулевое значение).

##  <a name="getcount"></a>  CMFCCmdUsageCount::GetCount

Получает счетчик использования, который сопоставлен заданному идентификатору команды.

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание:|
|*uiCmd*|[in] Идентификатор счетчика команду для извлечения.|

### <a name="return-value"></a>Возвращаемое значение

Счетчик использования, который сопоставлен заданному идентификатору команды.

##  <a name="hasenoughinformation"></a>  CMFCCmdUsageCount::HasEnoughInformation

Определяет ли этот объект получил минимальный объем данных отслеживания.

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если этот объект получил минимальный объем данных; отслеживания в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод возвращает ненулевое значение, если общее число `m_nTotalUsage`, из всех отслеживаемых команд является равным или больше, чем исходное количество `m_nStartCount`. По умолчанию платформа присваивает исходное количество 0. Это значение можно переопределить с помощью [CMFCCmdUsageCount::SetOptions](#setoptions) метод.

Этот метод используется [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) для определения, следует ли отображать все команды меню.

##  <a name="isfreqeuntlyusedcmd"></a>  CMFCCmdUsageCount::IsFreqeuntlyUsedCmd

Определяет, используется ли часто заданную команду.

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание:|
|*uiCmd*|[in] Указывает команду, чтобы проверить.|

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если команда часто используется; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод возвращает 0, если использование общее команды, `m_nTotalUsage`, равно 0. В противном случае этот метод возвращает ненулевое значение, если процент, из которых используется указанная команда больше, чем минимальный процент `m_nMinUsagePercentage`. По умолчанию платформа задает минимальный процент до 5. Это значение можно переопределить с помощью [CMFCCmdUsageCount::SetOptions](#setoptions) метод. Если минимальный процент равен 0, этот метод возвращает ненулевое значение, если указанная команда число больше 0.

[CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) этот метод используется для определения ли команды используется редко.

##  <a name="reset"></a>  CMFCCmdUsageCount::Reset

Удаляет счетчик использования всех команд.

```
void Reset();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы очистить все записи из структуры карты счетчиков команды `m_CmdUsage`и выполнить сброс использование общее команды, `m_nTotalUsage`, счетчик 0.

##  <a name="serialize"></a>  CMFCCmdUsageCount::Serialize

Считывает этот объект из архива или записывает его в архив.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*ar*|[in] Объект `CArchive` объект для сериализации в или из него.|

### <a name="remarks"></a>Примечания

Этот метод сериализует структуре карты счетчиков команда `m_CmdUsage`и об использовании общее команды, `m_nTotalUsage`, счетчик, в указанный архив или из него.

Примеры сериализации см. в разделе [сериализации: Сериализация объекта](../../mfc/serialization-serializing-an-object.md).

##  <a name="setoptions"></a>  CMFCCmdUsageCount::SetOptions

Общие наборы значений `CMFCCmdUsageCount` данные-члены класса.

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание:|
|*nStartCount*|[in] Новый исходное количество всех отслеживаемых команд.|
|*nMinUsagePercentage*|[in] Новый процент минимального срока использования.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно, значение FALSE при *nMinUsagePercentage* параметр, размер которого больше или равно 100.

### <a name="remarks"></a>Примечания

Этот метод задает общий `CMFCCmdUsageCount` данные-члены класса `m_nStartCount` и `m_nMinUsagePercentage` для *nStartCount* и *nMinUsagePercentage*, соответственно. `m_nStartCount` используется [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) метод, чтобы определить, собираются ли этот объект минимальный объем данных отслеживания. `m_nMinUsagePercentage` используется [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) метод для определения часто использовать заданную команду.

В отладочных сборках этот метод создает ошибку подтверждения, если *nMinUsagePercentage* параметр, размер которого больше или равно 100.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
