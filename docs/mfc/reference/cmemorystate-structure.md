---
title: Структура CMemoryState | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryState
dev_langs:
- C++
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba1d156d9453cd6a74a3543295d9d90d761e77f9
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040750"
---
# <a name="cmemorystate-structure"></a>Структура CMemoryState
Предоставляет удобный способ для обнаружения утечек памяти в приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|Создает структуру как класс, управляющий контрольными точками памяти.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMemoryState::Checkpoint](#checkpoint)|Получает снимок текущего состояния памяти (контрольных точек).|  
|[CMemoryState::Difference](#difference)|Вычисляет разницу между двумя объектами типа `CMemoryState`.|  
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|Выводит сводку всех объектов, выделенных на данный момент с момента предыдущей контрольной точки.|  
|[CMemoryState::DumpStatistics](#dumpstatistics)|Выводит статистику распределения памяти для `CMemoryState` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CMemoryState` Структура и не имеет базового класса.  
  
 «Утечку памяти» возникает, когда память для объекта в куче, но не освобождаются, когда он больше не требуется. Такие утечки памяти в конечном итоге могут привести к ошибкам нехватки памяти. Для выделения и освобождения памяти в приложении несколькими способами:  
  
-   С помощью `malloc` /  **свободного** семейства функций из библиотеки времени выполнения.  
  
-   С помощью функции управления памятью Windows API, **LocalAlloc**/ **LocalFree** и **GlobalAlloc**/ **GlobalFree** .  
  
-   С помощью C++ **новый** и **удалить** операторы.  
  
 `CMemoryState` Диагностики только помочь в обнаружении памяти выделенной памяти с помощью другой причиной утечек **новый** оператор не освобождается с помощью **удалить**. Две группы функций управления памятью, для программ не C++ и смешивания их с **новый** и **удалить** в одной программе не рекомендуется. Макрос дополнительные `DEBUG_NEW`, предоставляется для замены **новый** оператор, если вам требуется файл и номер строки отслеживания выделения памяти. `DEBUG_NEW` используется каждый раз, когда бы вы использовали **новый** оператор.  
  
 Как и в других диагностики `CMemoryState` диагностики доступны только в отладочной версии программы. Отладочная версия должна иметь **_DEBUG** константу.  
  
 Если есть подозрение, что программа существует утечка памяти, можно использовать `Checkpoint`, `Difference`, и `DumpStatistics` функции для обнаружения различий между состояниями памяти (объектов, выделенных) на двух различных этапах выполнения программы. Эта информация может быть удобно определять, является ли функция производит очистку всех объектов, которые он размещает.  
  
 Если просто знать, где дисбаланс в выделение и освобождение не предоставляет достаточно сведений, можно использовать `DumpAllObjectsSince` функции для помещения в дамп все объекты, размещенные с момента предыдущего вызова `Checkpoint`. Этот дамп показывает порядок выделения исходного файла и строки, где был выделен объект (Если вы используете `DEBUG_NEW` для выделения) и производным от объекта, его адрес и его размер. `DumpAllObjectsSince` также вызывает каждый объект `Dump` функции для предоставления сведений о текущем состоянии.  
  
 Дополнительные сведения об использовании `CMemoryState` и увидеть другие диагностики [отладки приложения MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Объявления объектов типа `CMemoryState` и вызовы функций-членов должно быть заключено `#if defined(_DEBUG)/#endif` директивы. В этом случае диагностики памяти, должны быть включены только в отладочных сборках программы.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CMemoryState`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="checkpoint"></a>  CMemoryState::Checkpoint  
 Делает снимок сводки памяти и сохраняет его в это `CMemoryState` объекта.  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>Примечания  
 `CMemoryState` Функции-члены [различие](#difference) и [DumpAllObjectsSince](#dumpallobjectssince) использования этих данных моментального снимка.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMemoryState](#cmemorystate) конструктор.  
  
##  <a name="cmemorystate"></a>  CMemoryState::CMemoryState  
 Создает пустой `CMemoryState` объекта, которое должно быть заполнено [контрольной точки](#checkpoint) или [различие](#difference) функции-члена.  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="difference"></a>  CMemoryState::Difference  
 Сравнивает два `CMemoryState` объектов, а затем сохраняет разницу в этот `CMemoryState` объекта.  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>Параметры  
 *oldState*  
 Состояние памяти, в соответствии с определением `CMemoryState` контрольной точки.  
  
 *новое состояние*  
 Новое состояние памяти в соответствии с `CMemoryState` контрольной точки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если отличаются в двух состояниях памяти; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 [Контрольная точка](#checkpoint) должна быть вызвана для каждого из этих двух параметров состояния памяти.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMemoryState](#cmemorystate) конструктор.  
  
##  <a name="dumpallobjectssince"></a>  CMemoryState::DumpAllObjectsSince  
 Вызовы `Dump` функции для всех объектов типа, производного от класса `CObject` , выделенные (и по-прежнему выделяются) с момента последнего [контрольной точки](#checkpoint) вызовите для этого `CMemoryState` объекта.  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>Примечания  
 Вызов `DumpAllObjectsSince` с помощью неинициализированного `CMemoryState` выгружать объекта не все объекты, которые в данный момент в памяти.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMemoryState](#cmemorystate) конструктор.  
  
##  <a name="dumpstatistics"></a>  CMemoryState::DumpStatistics  
 Печать отчета статистики четкими памяти из `CMemoryState` объект, который заполняется [различие](#difference) функции-члена.  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>Примечания  
 Отчет, в котором будет выведено на [afxDump](diagnostic-services.md#afxdump) устройство, отображается следующее:  
  
 Образец отчета содержит сведения о номер (или суммы) из:  
  
-   свободных блоков  
  
-   Обычные блоки  
  
-   CRT-блоки  
  
-   пропускаемые блоки  
  
-   клиентские блоки  
  
-   Максимальный объем памяти, используемой программой в любой момент времени (в байтах)  
  
-   общий объем памяти, в настоящее время используется в рамках программы (в байтах)  
  
 Свободные блоки — это блоки, освобождение которых задерживается, если число `afxMemDF` было задано значение **delayFreeMemDF**. Дополнительные сведения см. в разделе [afxMemDF](diagnostic-services.md#afxmemdf), в разделе «Макросов MFC и глобальные». В разделе [типы блоков в отладочной куче](http://msdn.microsoft.com/en-us/db2e7f62-0679-4b39-a23f-26f2c2f407c5) для Дополнительные сведения об этих типов блоков.  
  
### <a name="example"></a>Пример  
  Следующий код следует разместить в *projname*файле App.cpp. Определите следующие глобальные переменные:  
  
 [!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 В `InitInstance` функционировать, добавьте строку:  
  
 [!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 Добавление обработчика для `ExitInstance` функцией и используйте следующий код:  
  
 [!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 Теперь можно запускать программы в режиме отладки для просмотра выходных данных `DumpStatistics` функции.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



