---
title: "Поддержка IDispEventImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDispEventImpl
dev_langs: C++
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bf10a68ae15743a637df2dee52bee83c3dfcbe0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="supporting-idispeventimpl"></a>Поддержка IDispEventImpl
Класс шаблона [IDispEventImpl](../atl/reference/idispeventimpl-class.md) может использоваться для предоставления поддержки для приемников точек подключения в ATL класс. Приемник точки подключения позволяет классе для обработки событий, отправляемых с внешних COM-объектов. Эти приемники точки подключения, сопоставляются с картой приемника событий, предоставляемый класс.  
  
 Для правильной реализации приемника точки подключения для класса, необходимо выполнить следующие действия:  
  
-   Импорт библиотеки типов для каждого внешнего объекта.  
  
-   Объявите `IDispEventImpl` интерфейсов  
  
-   Объявите картой приемника событий  
  
-   Уведомлений и разъединения точки подключения  
  
 Шаги, необходимые для реализации приемник точки подключения выполняются путем изменения только файле заголовка (.h) этого класса.  
  
## <a name="importing-the-type-libraries"></a>Импорт библиотеки типов  
 Для каждого внешнего объекта события, для которого необходимо обработать необходимо импортировать библиотеку типов. Этот шаг определяет события, которые могут быть обработаны и предоставляет сведения, используемые при объявлении схеме приемника событий. [#Import](../preprocessor/hash-import-directive-cpp.md) директива может использоваться для выполнения этой задачи. Добавьте необходимые `#import` директивы строк для каждого интерфейса диспетчеризации, будет поддерживаться в файл заголовка (.h) этого класса.  
  
 В следующем примере импортируется библиотеки типов для внешнего сервера COM (`MSCAL.Calendar.7`):  
  
 [!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]  
  
> [!NOTE]
>  Необходимо создать отдельную `#import` инструкции для каждого внешнего типа библиотеки, будут поддерживать.  
  
## <a name="declaring-the-idispeventimpl-interfaces"></a>Объявление интерфейсов IDispEventImpl  
 Теперь, при импорте библиотеки типов для каждого интерфейса диспетчеризации, необходимо объявить отдельные `IDispEventImpl` интерфейсы для каждого внешнего интерфейса. Измените объявление класса, добавив `IDispEventImpl` объявление для каждого объекта внешнего интерфейса. Дополнительные сведения о параметрах см. в разделе [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
 В следующем коде объявляется два приемников точек подключения для `DCalendarEvents` интерфейса для COM-объекта, реализован классом `CMyCompositCtrl2`:  
  
 [!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]  
  
## <a name="declaring-an-event-sink-map"></a>Объявление картой приемника событий  
 В порядке для уведомлений о событиях, может быть обработано для правильной работы класса должен направлять каждое событие в его правильный обработчик. Это достигается путем объявления картой приемника событий.  
  
 Библиотека ATL предоставляет несколько макросов [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map), [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map), и [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex), который упростить это сопоставление. Стандартный формат выглядит следующим образом:  
  
 `BEGIN_SINK_MAP(comClass)`  
  
 `SINK_ENTRY_EX(id, iid, dispid, func)`  
  
 `. . . //additional external event entries`  
  
 `END_SINK_MAP()`  
  
 В следующем примере объявляется картой приемника событий с два обработчика событий:  
  
 [!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]  
  
 Реализация практически завершена. Последний шаг отвечает за авизующий и unadvising внешних интерфейсов.  
  
## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>О том и Unadvising IDispEventImpl интерфейсов  
 Последним шагом является реализация метод, который будет соединения (или разъединения) все точки соединения в соответствующие моменты времени. Это предупреждающее о том, необходимо выполнить до связи между внешним клиентам и объекта могут иметь место. Прежде чем объект становится видимым, каждого диспетчеризации внешний интерфейс, поддерживаемый объект запрашиваются исходящих интерфейсов. Установить подключение и ссылку на исходящий интерфейс используется для обработки событий из объекта. Эта процедура называется «о том,.»  
  
 По окончании работы объекта с внешних интерфейсов исходящих интерфейсов должны уведомляться, они больше не используется в классе. Этот процесс называется «unadvising».  
  
 Поскольку уникальный COM-объектов эта процедура варьируется в сведений и выполнение, между реализациями. Эти сведения выходят за рамки этой статьи и не описываются.  
  
## <a name="see-also"></a>См. также  
 [Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)

