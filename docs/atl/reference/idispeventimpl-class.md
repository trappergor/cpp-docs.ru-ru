---
title: "IDispEventImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl class"
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IDispEventImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет реализации методов `IDispatch`.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid= &IID_NULL,  
const GUID* plibid= &GUID_NULL,  
WORD wMajor= 0,  
WORD wMinor= 0,  
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE IDispEventImpl :  
public IDispEventSimpleImpl<nID, T, pdiid>  
```  
  
#### Параметры  
 `nID`  
 Уникальный идентификатор для исходного объекта.  При `IDispEventImpl` базовый класс для составного элемента управления, используйте идентификатор требуемого ресурса, содержащихся элементов управления для этого параметра.  В других случаях, используйте произвольное положительное целое число.  
  
 `T`  
 Класс, производный от `IDispEventImpl` пользователя.  
  
 `pdiid`  
 Указатель на идентификатор IID диспетчерский интерфейс события, реализуемого этим классом.  Этот интерфейс должен быть определен в библиотеке типов, указанной `plibid`, `wMajor` и `wMinor`.  
  
 `plibid`  
 Указатель на библиотеку типов, которая определяет интерфейс диспетчера указал на `pdiid`.  Если **&GUID\_NULL** библиотека типов будет загружено из поиска объекта события.  
  
 `wMajor`  
 Основной номер версии библиотеки типов.  Значение по умолчанию \- 0.  
  
 `wMinor`  
 Дополнительный номер версии библиотеки типов.  Значение по умолчанию \- 0.  
  
 `tihclass`  
 Класс, используемый для управления сведения о типе для `T`.  По умолчанию класс типа `CComTypeInfoHolder`; однако можно переопределить этот параметр шаблона, предоставляя класс типа, за исключением `CComTypeInfoHolder`.  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[IDispEventImpl::\_tihclass](../../atl/reference/idispeventimpl-class.md)|Класс, используемый для управления сведения о типе.  По умолчанию — `CComTypeInfoHolder`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[IDispEventImpl::IDispEventImpl](../Topic/IDispEventImpl::IDispEventImpl.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IDispEventImpl::GetFuncInfoFromId](../Topic/IDispEventImpl::GetFuncInfoFromId.md)|Находит индекс функции для заданного идентификатора диспетчера.|  
|[IDispEventImpl::GetIDsOfNames](../Topic/IDispEventImpl::GetIDsOfNames.md)|Сопоставляет один элемент и необязательный набор имен аргументов к соответствующему набору целого числа идентификаторов dispid.|  
|[IDispEventImpl::GetTypeInfo](../Topic/IDispEventImpl::GetTypeInfo.md)|Извлекает сведения о типе объекта.|  
|[IDispEventImpl::GetTypeInfoCount](../Topic/IDispEventImpl::GetTypeInfoCount.md)|Извлекает число интерфейсов сведений о типе.|  
|[IDispEventImpl::GetUserDefinedType](../Topic/IDispEventImpl::GetUserDefinedType.md)|Возвращает базовый тип пользовательского типа.|  
  
## Заметки  
 `IDispEventImpl` предоставляет способ реализации диспетчерский интерфейс события, не требуя указанных код реализации для каждого метода или события, в этом интерфейсе.  `IDispEventImpl` предоставляет реализации методов `IDispatch`.  Нужно только предоставить реализацию для событий, что нужно знать обработки.  
  
 Рабочие `IDispEventImpl` совместно с [сопоставление приемника событий](../Topic/BEGIN_SINK_MAP.md) в классе для направления события в соответствующее обработчик функции.  Использовать этот класс.  
  
 Добавить макрос [SINK\_ENTRY](../Topic/SINK_ENTRY.md) или [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md) к сопоставлению приемника событий для всех событий для каждого объекта, который необходимо обработать.  При использовании `IDispEventImpl` в качестве базового класса составного элемента управления можно вызвать [AtlAdviseSinkMap](../Topic/AtlAdviseSinkMap.md) для задания и критические соединение с источниками событий для всего сопоставления приемников записей в случае.  В других случаях или для больших элемента управления, [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) вызова для установки подключения между исходный объект, а базовый класс.  Вызов [DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) для прерывания соединение.  
  
 Необходимо наследовать `IDispEventImpl` \(с использованием уникальное значение для `nID`\) для каждого объекта, для которого нужно обрабатывать события.  Можно повторно использовать базовый класс, unadvising к одному объекту\-источнику затем советуя относительно другого объекта источника, но максимальное число исходных объектов, которые могут быть одним объектом обработаны одновременно ограничено числом базовых классов `IDispEventImpl`.  
  
 `IDispEventImpl` предоставляет те же функциональные возможности, что [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), за исключением того, что она возвращает сведения о типе об интерфейсе из библиотеки типов, а не его с предоставленными как указатель на структуру [\_ATL\_FUNC\_INFORMATION](../../atl/reference/atl-func-info-structure.md).  Используйте `IDispEventSimpleImpl` при отсутствии библиотеку типов, описывающую интерфейс события или не понадобиться, чтобы избежать издержек, связанных с использованием библиотеки типов.  
  
> [!NOTE]
>  `IDispEventImpl` и `IDispEventSimpleImpl` обеспечивают собственную реализацию **IUnknown::QueryInterface** что каждый базовый класс `IDispEventImpl` и `IDispEventSimpleImpl`, чтобы задействовать его как отдельный идентификатор модели COM, пока все еще, обеспечивая прямой доступ к членам класса в основном COM\-объект.  
  
 Реализация библиотеки ATL CE событий ActiveX только обозреватель типов тонет возвращаемые значения HRESULT или свободного пространства из методов обработчика событий; любое другое возвращаемое значение не поддерживается и его функциональности не определено.  
  
 Дополнительные сведения см. в разделе [Поддержка IDispEventImpl](../../atl/supporting-idispeventimpl.md).  
  
## Иерархия наследования  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [\_ATL\_FUNC\_INFO Structure](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl Class](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY](../Topic/SINK_ENTRY.md)   
 [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [Class Overview](../../atl/atl-class-overview.md)