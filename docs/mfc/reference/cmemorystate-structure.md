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
ms.openlocfilehash: a1a6912cd736643313306f6453ce19b1f6b97adc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502977"
---
# <a name="cmemorystate-structure"></a>Структура CMemoryState

Предоставляет удобный способ для обнаружения утечек памяти в приложении.

## <a name="syntax"></a>Синтаксис

```
struct CMemoryState
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMemoryState::CMemoryState](#cmemorystate)|Создает структуру стиле класса, которое управляет контрольных точек в памяти.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMemoryState::Checkpoint](#checkpoint)|Получает снимок текущего состояния памяти (контрольная точка).|
|[CMemoryState::Difference](#difference)|Вычисляет разницу между двумя объектами типа `CMemoryState`.|
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|Выводит сводку всех объектов, выделенных на данный момент с момента предыдущей контрольной точки.|
|[CMemoryState::DumpStatistics](#dumpstatistics)|Выводит статистику распределения памяти для `CMemoryState` объекта.|

## <a name="remarks"></a>Примечания

`CMemoryState` представляет собой структуру и не имеет базового класса.

«Утечку памяти» возникает, когда память для объекта в куче, но не освобождаются, когда он больше не требуется. Такие утечек памяти со временем может привести к ошибкам памяти. Существует несколько способов для выделения и освобождения памяти в приложении:

- С помощью `malloc` /  `free` семейства функций из библиотеки времени выполнения.

- С помощью функции управления памятью Windows API, `LocalAlloc` /  `LocalFree` и `GlobalAlloc` /  `GlobalFree`.

- С помощью C++ **новый** и **удалить** операторы.

`CMemoryState` Диагностики только помочь в обнаружении памяти утечек, вызываемых при выделении памяти с помощью **новый** оператор не освобождается с помощью **удалить**. Являются две группы функций управления памятью для программ не C++ и смешивания их с помощью **новый** и **удалить** в одной программе не рекомендуется. Дополнительные макрос, DEBUG_NEW, предоставляется для замены **новый** оператор при необходимости файл и номер строки отслеживания выделения памяти. DEBUG_NEW используется каждый раз, когда обычно используются **новый** оператор.

Как и другие диагностические `CMemoryState` диагностики доступны только в отладочных версиях программы. Отладочная версия необходимо определять константу _DEBUG.

Если вы подозреваете, приложении есть утечка памяти, можно использовать `Checkpoint`, `Difference`, и `DumpStatistics` функции для обнаружения различий между состояниями памяти (объектов, выделенных) на двух различных этапах выполнения программы. Эти сведения можно использовать при определении ли функция производит очистку всех объектов, которые он выделяет память.

Если просто знать, где происходит дисбаланс в выделение и освобождение не предоставляет достаточно сведений, можно использовать `DumpAllObjectsSince` функции для помещения в дамп все объекты, размещенные с момента предыдущего вызова `Checkpoint`. Этот дамп показывает порядок выделения, исходный файл и строки, где объект был выделен (Если вы используете DEBUG_NEW для выделения), и производным от объекта, его адрес и его размер. `DumpAllObjectsSince` также вызывает каждый объект `Dump` функции для предоставления сведений о текущем состоянии.

Дополнительные сведения об использовании `CMemoryState` и другие диагностические см. в разделе [отладка приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
>  Объявления объектов типа `CMemoryState` и вызовы функций-членов должно быть заключено в скобки `#if defined(_DEBUG)/#endif` директивы. В результате диагностики памяти должны быть включены только в отладочных сборках программы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CMemoryState`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="checkpoint"></a>  CMemoryState::Checkpoint

Создает моментальный снимок сводки памяти и сохраняет его в это `CMemoryState` объекта.

```
void Checkpoint();
```

### <a name="remarks"></a>Примечания

`CMemoryState` Функции-члены [различие](#difference) и [DumpAllObjectsSince](#dumpallobjectssince) использовать эти данные моментального снимка.

### <a name="example"></a>Пример

  См. в примере [CMemoryState](#cmemorystate) конструктор.

##  <a name="cmemorystate"></a>  CMemoryState::CMemoryState

Создает пустой `CMemoryState` объект, который должно быть заполнено [контрольной точки](#checkpoint) или [различие](#difference) функция-член.

```
CMemoryState();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

##  <a name="difference"></a>  CMemoryState::Difference

Сравнивает два `CMemoryState` объектов, а затем сохраняет разницу в данную коллекцию `CMemoryState` объекта.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>Параметры

*Сервера*<br/>
Состояние начального памяти согласно `CMemoryState` контрольной точки.

*новое состояние*<br/>
Новое состояние памяти в соответствии с `CMemoryState` контрольной точки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если двумя состояниями памяти различаются; в противном случае 0.

### <a name="remarks"></a>Примечания

[Контрольная точка](#checkpoint) должна быть вызвана для каждого из двух параметров состояния памяти.

### <a name="example"></a>Пример

  См. в примере [CMemoryState](#cmemorystate) конструктор.

##  <a name="dumpallobjectssince"></a>  CMemoryState::DumpAllObjectsSince

Вызовы `Dump` функции для всех объектов типа, производного от класса `CObject` , выделенных (и по-прежнему выделяются) с момента последнего [контрольной точки](#checkpoint) вызова для данного `CMemoryState` объекта.

```
void DumpAllObjectsSince() const;

```

### <a name="remarks"></a>Примечания

Вызов `DumpAllObjectsSince` с помощью неинициализированного `CMemoryState` объекта будет выгрузите все объекты в данный момент в памяти.

### <a name="example"></a>Пример

  См. в примере [CMemoryState](#cmemorystate) конструктор.

##  <a name="dumpstatistics"></a>  CMemoryState::DumpStatistics

Выводит краткую памяти статистический отчет из `CMemoryState` объект, который заполняется [различие](#difference) функция-член.

```
void DumpStatistics() const;

```

### <a name="remarks"></a>Примечания

Отчет, который будет выведено на экран [afxDump](diagnostic-services.md#afxdump) устройства, отображаются следующие:

Образец отчета содержит сведения о номер или сумма:

- свободных блоков

- обычных блоков

- Блоки CRT

- пропускаемые блоки

- клиентские блоки

- Максимальный объем памяти, используемой программой в любой момент времени (в байтах)

- общий объем памяти, которое используется в программе (в байтах)

Свободные блоки — это число блоков, освобождение которых задерживается, если `afxMemDF` было присвоено `delayFreeMemDF`. Дополнительные сведения см. в разделе [afxMemDF](diagnostic-services.md#afxmemdf), в разделе «Макросы MFC и глобальные».

### <a name="example"></a>Пример

  Следующий код должен быть помещен в *projname*файле App.cpp. Определите следующие глобальные переменные:

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

В `InitInstance` функции, добавьте строку:

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

Добавить обработчик для `ExitInstance` работать и с помощью следующего кода:

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

Теперь можно запустить программу в режиме отладки для просмотра выходных данных `DumpStatistics` функции.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

