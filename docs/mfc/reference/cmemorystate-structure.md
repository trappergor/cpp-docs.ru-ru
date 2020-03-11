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
ms.openlocfilehash: a110e1345cb970c117de125bd8105e1bc86eaf94
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855349"
---
# <a name="cmemorystate-structure"></a>Структура CMemoryState

Предоставляет удобный способ обнаружения утечек памяти в программе.

## <a name="syntax"></a>Синтаксис

```
struct CMemoryState
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CMemoryState:: CMemoryState](#cmemorystate)|Создает структуру, похожую на класс, которая управляет контрольными точками памяти.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CMemoryState:: Checkpoint](#checkpoint)|Получает моментальный снимок (контрольная точка) текущего состояния памяти.|
|[CMemoryState::D ифференце](#difference)|Вычисление разницы между двумя объектами типа `CMemoryState`.|
|[CMemoryState::D Умпаллобжектссинце](#dumpallobjectssince)|Выводит сводку всех объектов, выделенных в данный момент с момента создания предыдущей контрольной точки.|
|[CMemoryState::D Умпстатистикс](#dumpstatistics)|Печатает статистику выделения памяти для объекта `CMemoryState`.|

## <a name="remarks"></a>Remarks

`CMemoryState` является структурой и не имеет базового класса.

«Утечка памяти» возникает, когда память для объекта выделяется в куче, но не освобождается, если она больше не нужна. Такие утечки памяти могут в конечном итоге привести к ошибкам нехватки памяти. Существует несколько способов выделения и освобождения памяти в программе.

- Использование семейства функций `malloc`/ `free` из библиотеки времени выполнения.

- С помощью функций управления памятью API Windows `LocalAlloc`/ `LocalFree` и `GlobalAlloc`/ `GlobalFree`.

- C++ С помощью операторов **New** и **Delete** .

Диагностика `CMemoryState` помогает выявить утечки памяти, вызванные тем, что память, выделенная с помощью оператора **New** , не освобождается с помощью инструкции **Delete**. Две другие группы функций управления памятью предназначены дляC++ программ, не являющихся программами, и их смешивание с помощью **New** и **Delete** в одной программе не рекомендуется. Дополнительный макрос, DEBUG_NEW, используется для замены **нового** оператора, если требуется отслеживание количества операций выделения памяти для файлов и строк. DEBUG_NEW используется всякий раз, когда вы обычно используете оператор **New** .

Как и в случае с другими диагностическими данными, диагностика `CMemoryState` доступны только в отладочных версиях программы. Для отладочной версии должна быть определена константа _DEBUG.

Если предполагается, что программа имеет утечку памяти, можно использовать функции `Checkpoint`, `Difference`и `DumpStatistics`, чтобы узнать разницу между состоянием памяти (выделенными объектами) в двух разных точках выполнения программы. Эти сведения могут быть полезны при определении того, очищается ли функция от всех объектов, которые она выделяет.

Если просто узнать, где происходит дисбаланс при выделении и освобождении, не предоставляет достаточно сведений, можно использовать функцию `DumpAllObjectsSince` для дампа всех объектов, выделенных с момента предыдущего вызова `Checkpoint`. Этот дамп показывает порядок выделения, исходный файл и строку, в которой был выделен объект (если используется DEBUG_NEW для выделения) и наследование объекта, его адрес и размер. `DumpAllObjectsSince` также вызывает функцию `Dump` каждого объекта, чтобы предоставить сведения о его текущем состоянии.

Дополнительные сведения об использовании `CMemoryState` и других диагностических данных см. в разделе [Отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
>  Объявления объектов типа `CMemoryState` и вызовы функций членов должны быть заключены в квадратные директивы `#if defined(_DEBUG)/#endif`. Это приводит к тому, что диагностика памяти будет включена только в отладочных сборках программы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CMemoryState`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="checkpoint"></a>CMemoryState:: Checkpoint

Создает сводку по снимкам памяти и сохраняет ее в этом `CMemoryState` объекте.

```
void Checkpoint();
```

### <a name="remarks"></a>Remarks

`CMemoryState`ные функции элементов [различаются](#difference) и [DumpAllObjectsSince](#dumpallobjectssince) использовать эти данные моментального снимка.

### <a name="example"></a>Пример

  См. пример для конструктора [CMemoryState](#cmemorystate) .

##  <a name="cmemorystate"></a>CMemoryState:: CMemoryState

Создает пустой объект `CMemoryState`, который должен быть заполнен функцией члена [контрольной точки](#checkpoint) или [разности](#difference) .

```
CMemoryState();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

##  <a name="difference"></a>CMemoryState::D ифференце

Сравнивает два `CMemoryState` объектов, а затем сохраняет разность в этом `CMemoryState` объекте.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>Параметры

*олдстате*<br/>
Начальное состояние памяти, определенное `CMemoryState` контрольной точкой.

*newState*<br/>
Новое состояние памяти, определенное `CMemoryState` контрольной точкой.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если два состояния памяти различаются; в противном случае — 0.

### <a name="remarks"></a>Remarks

Для каждого из двух параметров состояния памяти должна быть вызвана [контрольная точка](#checkpoint) .

### <a name="example"></a>Пример

  См. пример для конструктора [CMemoryState](#cmemorystate) .

##  <a name="dumpallobjectssince"></a>CMemoryState::D Умпаллобжектссинце

Вызывает функцию `Dump` для всех объектов типа, производных от класса `CObject`, которые были выделены (и по-прежнему выделены) с момента последнего вызова [контрольной точки](#checkpoint) для данного объекта `CMemoryState`.

```
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>Remarks

При вызове `DumpAllObjectsSince` с неинициализированным `CMemoryState` объектом будут выгружены все объекты, находящиеся в памяти.

### <a name="example"></a>Пример

  См. пример для конструктора [CMemoryState](#cmemorystate) .

##  <a name="dumpstatistics"></a>CMemoryState::D Умпстатистикс

Выводит отчет о краткой статистике памяти из объекта `CMemoryState`, который заполняется функцией-членом [разности](#difference) .

```
void DumpStatistics() const;
```

### <a name="remarks"></a>Remarks

Отчет, который печатается на устройстве [афксдумп](diagnostic-services.md#afxdump) , содержит следующие сведения:

Образец отчета содержит сведения о количестве (или объеме):

- свободные блоки

- нормальные блоки

- Блоки CRT

- игнорировать блоки

- клиентские блоки

- максимальный объем памяти, используемый программой в любой момент времени (в байтах)

- Общий объем используемой программой памяти (в байтах)

Свободные блоки — это число блоков, освобождение которых было отложено, если для `afxMemDF` было задано значение `delayFreeMemDF`. Дополнительные сведения см. в статье [afxMemDF](diagnostic-services.md#afxmemdf)в разделе "макросы и глобальные библиотеки MFC".

### <a name="example"></a>Пример

  Следующий код следует поместить в приложение *ProjName*. cpp. Определите следующие глобальные переменные:

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

В функции `InitInstance` добавьте строку:

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

Добавьте обработчик для функции `ExitInstance` и используйте следующий код:

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

Теперь можно запустить программу в режиме отладки, чтобы просмотреть выходные данные функции `DumpStatistics`.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
