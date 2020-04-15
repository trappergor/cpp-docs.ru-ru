---
title: Структура CMemoryState
ms.date: 11/04/2016
f1_keywords:
- CMemoryState
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
ms.openlocfilehash: 8f49a9faf70673c62167deeaa1bef33e4882378f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369990"
---
# <a name="cmemorystate-structure"></a>Структура CMemoryState

Предоставляет удобный способ обнаружения утечек памяти в вашей программе.

## <a name="syntax"></a>Синтаксис

```
struct CMemoryState
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMemoryState::Состояние памяти](#cmemorystate)|Строит структуру, похожую на класс, которая контролирует контроль над контрольными точками памяти.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMemoryState::Checkpoint](#checkpoint)|Получает моментальный снимок (контрольный пункт) текущего состояния памяти.|
|[CMemoryState::Difference](#difference)|Вычисляет разницу между `CMemoryState`двумя объектами типа.|
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|Сбрасывает резюме всех в настоящее время выделенных объектов с предыдущего контрольно-пропускного пункта.|
|[CMemoryState::DumpStatistics](#dumpstatistics)|Печать статистики распределения `CMemoryState` памяти для объекта.|

## <a name="remarks"></a>Remarks

`CMemoryState`является структурой и не имеет базового класса.

"Утечка памяти" происходит, когда память для объекта выделяется на куче, но не разослана, когда она больше не требуется. Такие утечки памяти могут в конечном итоге привести к ошибкам вне памяти. Есть несколько способов выделения и дераспределения памяти в вашей программе:

- /  `free` Использование семейства функций из библиотеки `malloc` времени выполнения.

- Использование функций управления памятью `LocalAlloc` /  `LocalFree` `GlobalAlloc` /  `GlobalFree`Windows API и

- Использование новых операторов и **удалений** с помощью **новых** операторов.

Диагностика `CMemoryState` помогает обнаруживать утечки памяти, вызванные тем, что память, выделенная с помощью **нового** оператора, не разослана с помощью **удаления.** Две другие группы функций управления памятью предназначены для не-СЗ программ, и смешивание их с **новыми** и **удалить** в той же программе не рекомендуется. Дополнительный макрос, DEBUG_NEW, предоставляется для замены **нового** оператора, когда вам нужно файл и номер строки отслеживания распределения памяти. DEBUG_NEW используется всякий раз, когда вы обычно используете **нового** оператора.

Как и в других `CMemoryState` диагностических средствах, диагностика доступна только в версиях отладки вашей программы. Версия отладки должна иметь _DEBUG констант.

Если вы подозреваете, что ваша программа `Checkpoint`имеет `Difference`утечку памяти, вы можете использовать, и `DumpStatistics` функции, чтобы обнаружить разницу между состоянием памяти (объекты выделены) в двух различных точках в выполнении программы. Эта информация может быть полезна для определения того, очищает ли функция все объекты, которые она выделяет.

Если просто знать, где происходит дисбаланс в распределении и размещении дел, не предоставляет достаточно информации, вы можете использовать `DumpAllObjectsSince` функцию для сброса всех объектов, выделенных с момента предыдущего `Checkpoint`вызова. Эта свалка показывает порядок распределения, исходный файл и строку, где объект был выделен (если вы используете DEBUG_NEW для распределения), и производные объекта, его адрес и его размер. `DumpAllObjectsSince`также вызывает функцию `Dump` каждого объекта, чтобы предоставить информацию о его текущем состоянии.

Для получения дополнительной информации о том, как использовать `CMemoryState` и другие диагностические данные, см. [Debugging MFC Applications](/visualstudio/debugger/mfc-debugging-techniques)

> [!NOTE]
> Объявления объектов типа `CMemoryState` и вызовы к функциям `#if defined(_DEBUG)/#endif` членов должны быть скобками директивами. Это приводит к тому, что диагностика памяти включается только в отладку сборки программы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CMemoryState`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cmemorystatecheckpoint"></a><a name="checkpoint"></a>CMemoryState::Checkpoint

Принимает сводку памяти и `CMemoryState` хранит ее в этом объекте.

```
void Checkpoint();
```

### <a name="remarks"></a>Remarks

Участник `CMemoryState` функции [Разница](#difference) и [DumpAllObjectsSince](#dumpallobjectssince) использовать эти данные моментального снимка.

### <a name="example"></a>Пример

  Смотрите пример для конструктора [CMemoryState.](#cmemorystate)

## <a name="cmemorystatecmemorystate"></a><a name="cmemorystate"></a>CMemoryState::Состояние памяти

Строит пустой `CMemoryState` объект, который должен быть заполнен функцией [Checkpoint](#checkpoint) или [Difference.](#difference)

```
CMemoryState();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

## <a name="cmemorystatedifference"></a><a name="difference"></a>CMemoryState::Difference

Сравнивает `CMemoryState` два объекта, а затем `CMemoryState` хранит разницу в этом объекте.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>Параметры

*староегосударство*<br/>
Начальное состояние памяти, `CMemoryState` определенное контрольно-пропускной точкой.

*Новое_состояние*<br/>
Новое состояние памяти, `CMemoryState` определенное контрольно-пропускной точкой.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если два состояния памяти отличаются; в противном случае 0.

### <a name="remarks"></a>Remarks

[Контрольно-пропускной пункт](#checkpoint) должен быть вызван для каждого из двух параметров состояния памяти.

### <a name="example"></a>Пример

  Смотрите пример для конструктора [CMemoryState.](#cmemorystate)

## <a name="cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>CMemoryState::DumpAllObjectsSince

Вызывает `Dump` функцию для всех объектов типа, полученных из класса, `CObject` которые были выделены (и все еще выделены) с момента последнего вызова [Checkpoint](#checkpoint) для этого `CMemoryState` объекта.

```
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>Remarks

Вызов `DumpAllObjectsSince` с неиницефицированным `CMemoryState` объектом будет сбрасывать все объекты, наданные в настоящее время в памяти.

### <a name="example"></a>Пример

  Смотрите пример для конструктора [CMemoryState.](#cmemorystate)

## <a name="cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>CMemoryState::DumpStatistics

Печать краткого отчета статистики памяти с `CMemoryState` объекта, заполненного функцией участника [Разницы.](#difference)

```
void DumpStatistics() const;
```

### <a name="remarks"></a>Remarks

Отчет, напечатанный на устройстве [afxDump,](diagnostic-services.md#afxdump) показывает следующее:

В выборочной отчете приводится информация о количестве (или размере):

- бесплатные блоки

- нормальные блоки

- Блоки CRT

- игнорировать блоки

- клиентские блоки

- максимальная память, используемая программой в любой момент времени (в байтах)

- общая память, используемая в настоящее время программой (в байтах)

Бесплатные блоки - это количество блоков, сделки которых были отложены, если `afxMemDF` он был установлен на `delayFreeMemDF`. Для получения дополнительной информации, [см. afxMemDF](diagnostic-services.md#afxmemdf), в разделе "MFC Макрос и Глобалс".

### <a name="example"></a>Пример

  Следующий код должен быть помещен в *projname*App.cpp. Определите следующие глобальные переменные:

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

В `InitInstance` функции добавьте строку:

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

Добавьте обработчик для функции `ExitInstance` и используйте следующий код:

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

Теперь можно запустить программу в режиме Debug, чтобы увидеть выход функции. `DumpStatistics`

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
