---
title: "IDispEventSimpleImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispEventSimpleImpl"
  - "ATL::IDispEventSimpleImpl"
  - "ATL.IDispEventSimpleImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventSimpleImpl class"
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDispEventSimpleImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет реализации методов `IDispatch` без получения сведений о типе из библиотеки типов.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid  
>  
class ATL_NO_VTABLE IDispEventSimpleImpl :  
public _IDispEventLocator<nID, pdiid>  
```  
  
#### Параметры  
 `nID`  
 Уникальный идентификатор для исходного объекта.  При `IDispEventSimpleImpl` базовый класс для составного элемента управления, используйте идентификатор требуемого ресурса, содержащихся элементов управления для этого параметра.  В других случаях, используйте произвольное положительное целое число.  
  
 `T`  
 Класс, производный от `IDispEventSimpleImpl` пользователя.  
  
 `pdiid`  
 Указатель на идентификатор IID диспетчерский интерфейс события, реализуемого этим классом.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IDispEventSimpleImpl::Advise](../Topic/IDispEventSimpleImpl::Advise.md)|Устанавливает соединение с источником событий по умолчанию.|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|Устанавливает соединение с источником события.|  
|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|Разрывает соединение с источником события.|  
|[IDispEventSimpleImpl::GetIDsOfNames](../Topic/IDispEventSimpleImpl::GetIDsOfNames.md)|Возвращает **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfo](../Topic/IDispEventSimpleImpl::GetTypeInfo.md)|Возвращает **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](../Topic/IDispEventSimpleImpl::GetTypeInfoCount.md)|Возвращает **E\_NOTIMPL**.|  
|[IDispEventSimpleImpl::Invoke](../Topic/IDispEventSimpleImpl::Invoke.md)|Вызывает перечисляемое обработчиками событий в случае сопоставление приемников.|  
|[IDispEventSimpleImpl::Unadvise](../Topic/IDispEventSimpleImpl::Unadvise.md)|Разрывает соединение с источником событий по умолчанию.|  
  
## Заметки  
 `IDispEventSimpleImpl` предоставляет способ реализации диспетчерский интерфейс события, не требуя указанных код реализации для каждого метода или события, в этом интерфейсе.  `IDispEventSimpleImpl` предоставляет реализации методов `IDispatch`.  Нужно только предоставить реализацию для событий, что нужно знать обработки.  
  
 Рабочие `IDispEventSimpleImpl` совместно с [сопоставление приемника событий](../Topic/BEGIN_SINK_MAP.md) в классе для направления события в соответствующее обработчик функции.  Использовать этот класс.  
  
-   Добавить макрос [SINK\_ENTRY\_INFORMATION](../Topic/SINK_ENTRY_INFO.md) к сопоставлению приемника событий для всех событий для каждого объекта, который необходимо обработать.  
  
-   Предоставляет сведения о типе для каждого события, передавая указатель на структуру [\_ATL\_FUNC\_INFORMATION](../../atl/reference/atl-func-info-structure.md) в качестве параметра для каждой записи.  На платформах x86, значение `_ATL_FUNC_INFO.cc` должно быть CC\_CDECL с функция обратного вызова при вызове метода \_\_stdcall.  
  
-   Вызовите [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) для установки подключения между исходный объект, а базовый класс.  
  
-   Вызов [DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) для прерывания соединение.  
  
 Необходимо наследовать `IDispEventSimpleImpl` \(с использованием уникальное значение для `nID`\) для каждого объекта, для которого нужно обрабатывать события.  Можно повторно использовать базовый класс, unadvising к одному объекту\-источнику затем советуя относительно другого объекта источника, но максимальное число исходных объектов, которые могут быть одним объектом обработаны одновременно ограничено числом базовых классов `IDispEventSimpleImpl`.  
  
 **IDispEventSimplImpl** предоставляет те же функциональные возможности, что [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), за исключением того, что она не получает сведения о типе об интерфейсе из библиотеки типов.  Мастеры создают код на основе только на `IDispEventImpl`, но можно использовать `IDispEventSimpleImpl` путем добавления кода вручную.  Используйте `IDispEventSimpleImpl` при отсутствии библиотеку типов, описывающую интерфейс события или не понадобиться, чтобы избежать издержек, связанных с использованием библиотеки типов.  
  
> [!NOTE]
>  `IDispEventImpl` и `IDispEventSimpleImpl` обеспечивают собственную реализацию **IUnknown::QueryInterface** что каждый базовый класс `IDispEventImpl` или `IDispEventSimpleImpl`, чтобы задействовать его как отдельный идентификатор модели COM, пока все еще, обеспечивая прямой доступ к членам класса в основном COM\-объект.  
  
 Реализация библиотеки ATL CE событий ActiveX только обозреватель типов тонет возвращаемые значения HRESULT или свободного пространства из методов обработчика событий; любое другое возвращаемое значение не поддерживается и его функциональности не определено.  
  
 Дополнительные сведения см. в разделе [Поддержка IDispEventImpl](../../atl/supporting-idispeventimpl.md).  
  
## Иерархия наследования  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [\_ATL\_FUNC\_INFO Structure](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl Class](../../atl/reference/idispeventimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [Class Overview](../../atl/atl-class-overview.md)