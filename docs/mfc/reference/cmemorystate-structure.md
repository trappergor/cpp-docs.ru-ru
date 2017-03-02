---
title: "Структура CMemoryState | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryState
dev_langs:
- C++
helpviewer_keywords:
- CMemoryState structure
- memory leaks, detecting
- detecting memory leaks
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 037c8f075a14346e3428c5e19bfda662c4f3c2b0
ms.lasthandoff: 02/24/2017

---
# <a name="cmemorystate-structure"></a>Структура CMemoryState
Предоставляет удобный способ для обнаружения утечек памяти в приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|Создает структуру подобный класс, управляющий контрольными точками памяти.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemoryState::Checkpoint](#checkpoint)|Получает снимок текущего состояния памяти (контрольная точка).|  
|[CMemoryState::Difference](#difference)|Вычисляет разницу между двумя объектами типа `CMemoryState`.|  
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|Выводит сводку всех объектов, выделенных на данный момент со времени предыдущей контрольной точки.|  
|[CMemoryState::DumpStatistics](#dumpstatistics)|Выводит статистику распределения памяти для `CMemoryState` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CMemoryState`представляет собой структуру и не имеет базового класса.  
  
 «Утечку памяти» возникает, когда память для объекта в куче, но не освобождаются, когда он больше не требуется. Такие утечки памяти со временем может привести к ошибкам нехватки памяти. Для выделения и освобождения памяти в приложении несколькими способами:  
  
-   С помощью `malloc` /  **свободного** семейства функций из библиотеки времени выполнения.  
  
-   С помощью функции управления памятью Windows API, **LocalAlloc**/ **LocalFree** и **GlobalAlloc**/ **GlobalFree**.  
  
-   С помощью C++ **новый** и **удаление** операторы.  
  
 `CMemoryState` Диагностики только помогает обнаружить памяти выделенной памяти с помощью другой причиной утечек **новый** оператор не освобождается с помощью **удаление**. Две группы функций управления памятью, для программ не C++ и смешивания их с **новый** и **удаление** в той же программе не рекомендуется. Дополнительные макрос `DEBUG_NEW`, предоставляется для замены **новый** оператор при необходимости файл и номер строки отслеживания выделения памяти. `DEBUG_NEW`используется, когда обычно используются **новый** оператор.  
  
 Как и в других диагностики `CMemoryState` диагностики доступны только в отладочной версии программы. Отладочная версия должен иметь **_DEBUG** константу.  
  
 Если есть подозрение, что программа существует утечка памяти, можно использовать `Checkpoint`, **различие**, и `DumpStatistics` функции для обнаружения различий между состояниями памяти (объектов, выделенных) на двух различных этапах выполнения программы. Эти сведения можно использовать при определении ли функция производит очистку всех объектов, которые он выделяет память.  
  
 Если просто знать, где дисбаланс в выделение и освобождение не предоставляет достаточно сведений, можно использовать `DumpAllObjectsSince` функции для помещения в дамп все объекты, размещенные с момента предыдущего вызова `Checkpoint`. Этот дамп показывает порядок выделения исходного файла и строки, где был выделен объект (при использовании `DEBUG_NEW` для выделения) и производным от объекта, его адрес и его размер. `DumpAllObjectsSince`также вызывает каждый объект `Dump` функции для предоставления сведений о текущем состоянии.  
  
 Дополнительные сведения об использовании `CMemoryState` и увидеть другие диагностики [отладка приложений MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Объявления объектов типа `CMemoryState` и вызовы функций-членов должно быть заключено в скобки `#if defined(_DEBUG)/#endif` директивы. В результате диагностики памяти должны быть включены только в отладочных сборках программы.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CMemoryState`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="a-namecheckpointa--cmemorystatecheckpoint"></a><a name="checkpoint"></a>CMemoryState::Checkpoint  
 Создание моментального снимка сводки памяти и сохраняет его в этом `CMemoryState` объекта.  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>Примечания  
 `CMemoryState` Функции-члены [различие](#difference) и [DumpAllObjectsSince](#dumpallobjectssince) использовать эти данные моментального снимка.  
  
### <a name="example"></a>Пример  
  В примере показано [CMemoryState](#cmemorystate) конструктор.  
  
##  <a name="a-namecmemorystatea--cmemorystatecmemorystate"></a><a name="cmemorystate"></a>CMemoryState::CMemoryState  
 Создает пустой `CMemoryState` объекта, которое должно быть заполнено [контрольной точки](#checkpoint) или [различие](#difference) функции-члена.  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities&18;](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="a-namedifferencea--cmemorystatedifference"></a><a name="difference"></a>CMemoryState::Difference  
 Сравнивает два `CMemoryState` объектов, а затем сохраняет разницу в эту `CMemoryState` объекта.  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>Параметры  
 *oldState*  
 Состояние памяти определяется `CMemoryState` контрольной точки.  
  
 *новое состояние*  
 Новое состояние памяти в соответствии с `CMemoryState` контрольной точки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если двумя состояниями памяти различаются; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 [Контрольная точка](#checkpoint) должна быть вызвана для каждого из двух параметров состояния памяти.  
  
### <a name="example"></a>Пример  
  В примере показано [CMemoryState](#cmemorystate) конструктор.  
  
##  <a name="a-namedumpallobjectssincea--cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>CMemoryState::DumpAllObjectsSince  
 Вызовы `Dump` функции для всех объектов типа, производного от класса `CObject` , выделенные (и по-прежнему выделяются) с момента последнего [контрольной точки](#checkpoint) вызова для этого `CMemoryState` объекта.  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>Примечания  
 Вызов `DumpAllObjectsSince` с неинициализированной `CMemoryState` объекта будет дамп всех объектов в данный момент в памяти.  
  
### <a name="example"></a>Пример  
  В примере показано [CMemoryState](#cmemorystate) конструктор.  
  
##  <a name="a-namedumpstatisticsa--cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>CMemoryState::DumpStatistics  
 Печать отчета статистики четкими памяти из `CMemoryState` объект, который заполняется [различие](#difference) функции-члена.  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>Примечания  
 Отчет, в котором будет выведено на [afxDump](http://msdn.microsoft.com/library/4b3cfa3f-fb75-456a-9d99-a5601acbcb11) устройство, отображается следующее:  
  
 Образец отчета предоставляет сведения об номер (или суммы):  
  
-   свободных блоков  
  
-   Обычные блоки  
  
-   CRT-блоки  
  
-   пропускаемые блоки  
  
-   клиентские блоки  
  
-   Максимальный объем памяти, используемой программой в любой момент времени (в байтах)  
  
-   общий объем памяти, в настоящее время используется программой (в байтах)  
  
 Свободные блоки — это блоки, освобождение которых задерживается, если число `afxMemDF` было задано значение **delayFreeMemDF**. Дополнительные сведения см. в разделе [afxMemDF](diagnostic-services.md#afxmemdf), в разделе «Макросы MFC и глобальные». В разделе [типы блоков в отладочной куче](http://msdn.microsoft.com/en-us/db2e7f62-0679-4b39-a23f-26f2c2f407c5) блоке Дополнительные сведения об этих типов.  
  
### <a name="example"></a>Пример  
  Данный код следует поместить в *имяПроекта*файле App.cpp. Определите следующие глобальные переменные:  
  
 [!code-cpp[NVC_MFC_Utilities&#40;](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 В `InitInstance` функцию, добавьте строку:  
  
 [!code-cpp[NVC_MFC_Utilities&#41;](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 Добавьте обработчик для `ExitInstance` функции и используйте следующий код:  
  
 [!code-cpp[NVC_MFC_Utilities&#42;](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 Теперь можно запустить программу в режиме отладки, чтобы просмотреть выходные данные `DumpStatistics` функции.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




