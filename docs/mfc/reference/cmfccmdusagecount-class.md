---
title: CMFCCmdUsageCount Класс
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
ms.openlocfilehash: 02b302ec38922128190a6f20ce2f156b52383b55
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752580"
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount Класс

Отслеживает количество сообщений Windows, например, когда пользователь выбирает элемент из меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Конструктор по умолчанию.|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Приращения по одному счетчику, который связан с данной командой.|
|[CMFCCmdUsageCount::GetCount](#getcount)|Извлекает количество использования, связанное с данным идентификатором команды.|
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Определяет, собрал ли этот объект минимальное количество данных отслеживания.|
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Определяет, часто ли используется данная команда.|
|[CMFCCmdUsageCount::Перезагрузка](#reset)|Очищает количество использования всех команд.|
|[CMFCCmdUsageCount::: Сериал](#serialize)|Читает этот объект из архива или запишет его в архив. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Устанавливает значения общих `CMFCCmdUsageCount` членов данных класса.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|Имя|Описание|
|`m_CmdUsage`|Объект, `CMap` который отображает команды к их использованию, имеет значение.|
|`m_nMinUsagePercentage`|Минимальный процент использования для часто используемой команды.|
|`m_nStartCount`|Счетчик запуска, используемый для определения того, собрал ли этот объект минимальное количество данных отслеживания.|
|`m_nTotalUsage`|Количество всех отслеживаемых команд.|

### <a name="remarks"></a>Remarks

Класс `CMFCCmdUsageCount` отображает каждый числовый идентификатор сообщения Windows с 32-битным неподписанным счетчиком. `CMFCToolBar`использует этот класс для отображения часто используемых элементов панели инструментов. Для получения `CMFCToolBar`дополнительной информации о, см. [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)

Можно сохранять `CMFCCmdUsageCount` данные классов между запусками программы. Используйте [CMFCCmdUsageCount::Serialize](#serialize) метод сериализации данных членов класса и [CMFCCmdUsageCount::SetOptions](#setoptions) метод для установки общих данных члена.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcmdusagecount.h

## <a name="cmfccmdusagecountaddcmd"></a><a name="addcmd"></a>CMFCCmdUsageCount::AddCmd

Приращения по одному счетчику, который связан с данной командой.

```cpp
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*uiCmd*|(в) Определяет счетчик команды на приращение.|

### <a name="remarks"></a>Remarks

Этот метод добавляет новую запись в структуру карты командных отсчетов, `m_CmdUsage`если запись еще не существует.

Этот метод ничего не делает в следующих случаях:

- Платформа панели инструментов находится в режиме настройки (метод [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) возвращает ненулевое значение).

- Команда относится к сепаратору подменю или меню *(uiCmd* равен 0 или -1).

- *uiCmd* относится к стандартной `IsStandardCommand` команде (глобальная функция возвращает ненулевое значение).

## <a name="cmfccmdusagecountgetcount"></a><a name="getcount"></a>CMFCCmdUsageCount::GetCount

Извлекает количество использования, связанное с данным идентификатором команды.

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*uiCmd*|(в) Идентификатор счетчика команды для извлечения.|

### <a name="return-value"></a>Возвращаемое значение

Количество использования, связанное с данным идентификатором команды.

## <a name="cmfccmdusagecounthasenoughinformation"></a><a name="hasenoughinformation"></a>CMFCCmdUsageCount::HasEnoughInformation

Определяет, получил ли этот объект минимальное количество данных отслеживания.

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если этот объект получил минимальное количество данных отслеживания; в противном случае 0.

### <a name="remarks"></a>Remarks

Этот метод возвращает ненулевое значение, `m_nTotalUsage`если общее количество всех отслеживаемых команд равно `m_nStartCount`или больше первоначального количества. По умолчанию фреймворк устанавливает исходное количество 0. Вы можете переопределить это значение с помощью метода [CMFCCmdUsageCount::SetOptions.](#setoptions)

Этот метод используется [CMFCMenuBar::IsShowAllCommands,](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) чтобы определить, следует ли показывать все доступные команды меню.

## <a name="cmfccmdusagecountisfreqeuntlyusedcmd"></a><a name="isfreqeuntlyusedcmd"></a>CMFCCmdUsageCount::IsFreqeuntlyUsedCmd

Определяет, часто ли используется данная команда.

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*uiCmd*|(в) Определяет команду для проверки.|

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если команда часто используется; в противном случае 0.

### <a name="remarks"></a>Remarks

Этот метод возвращает 0, если `m_nTotalUsage`общее использование команды, 0. В противном случае этот метод возвращается ненулевой, если процент, `m_nMinUsagePercentage`из которого используется указанная команда, больше минимального процента. По умолчанию фреймворк устанавливает минимальный процент до 5. Вы можете переопределить это значение с помощью метода [CMFCCmdUsageCount::SetOptions.](#setoptions) Если минимальный процент составляет 0, этот метод возвращается ненулевой, если указанный подсчет команд превышает 0.

[CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) использует этот метод, чтобы определить, редко ли используется команда.

## <a name="cmfccmdusagecountreset"></a><a name="reset"></a>CMFCCmdUsageCount::Перезагрузка

Очищает количество использования всех команд.

```cpp
void Reset();
```

### <a name="remarks"></a>Remarks

Вызов иметод, чтобы очистить все записи из `m_CmdUsage`структуры карты командных отсчетов, и сбросить общее использование команды, `m_nTotalUsage`, счетчик 0.

## <a name="cmfccmdusagecountserialize"></a><a name="serialize"></a>CMFCCmdUsageCount::: Сериал

Читает этот объект из архива или записывает его в архив.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*ar*|(в) Объект `CArchive` для сериализации из или в.|

### <a name="remarks"></a>Remarks

Этот метод сериализирует структуру карты `m_CmdUsage`командных подсчетов, `m_nTotalUsage`а также общее использование команды, счетчик от или к указанному архиву.

Для примеров сериализации [см. Сериализация: Сериализация объекта](../../mfc/serialization-serializing-an-object.md).

## <a name="cmfccmdusagecountsetoptions"></a><a name="setoptions"></a>CMFCCmdUsageCount::SetOptions

Устанавливает значения общих `CMFCCmdUsageCount` членов данных класса.

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*nStartCount*|(в) Новый первоначальный подсчет всех отслеживаемых команд.|
|*nMinUsageПроцент*|(в) Новый минимальный процент использования.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод удается, FALSE, если *nMinUsageПроцент* параметр больше или равна 100.

### <a name="remarks"></a>Remarks

Этот метод устанавливает `CMFCCmdUsageCount` общих `m_nStartCount` `m_nMinUsagePercentage` членов данных класса и *nStartCount* и *nMinUsagePercentage*, соответственно. `m_nStartCount`используется [методом CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) метод, чтобы определить, является ли этот объект собрал минимальное количество данных отслеживания. `m_nMinUsagePercentage`используется [методом CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) метод, чтобы определить, часто ли используется данная команда.

В сборке Debug этот метод генерирует сбой утверждения, если параметр *nMinUsagePercentage* больше или равен 100.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
