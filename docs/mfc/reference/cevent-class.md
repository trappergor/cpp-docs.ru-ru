---
title: "CEvent Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CEvent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEvent class"
  - "классы синхронизации, CEvent class"
  - "synchronization objects, event"
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
caps.latest.revision: 27
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEvent Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет событие, объект синхронизации, позволяющий один поток, чтобы уведомить другие, что произошло событие.  
  
## Синтаксис  
  
```  
class CEvent : public CSyncObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CEvent::CEvent](../Topic/CEvent::CEvent.md)|Создает объект `CEvent`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CEvent::PulseEvent](../Topic/CEvent::PulseEvent.md)|Устанавливает событие в сигнальное доступному \(\), потоки в состоянии ожидания выпусков и наборам событие к отсутствующему \(nonsignaled\).|  
|[CEvent::ResetEvent](../Topic/CEvent::ResetEvent.md)|Устанавливает событие к отсутствующему \(nonsignaled\).|  
|[CEvent::SetEvent](../Topic/CEvent::SetEvent.md)|Устанавливает событие в сигнальное доступные выпуски \(\) и всех потоков в состоянии ожидания.|  
|[CEvent::Unlock](../Topic/CEvent::Unlock.md)|Освобождает объект события.|  
  
## Заметки  
 События полезны, когда поток должен знать, когда для выполнения задачи.  Например, поток, в котором данные копируются в архив данных следует уведомить, когда новые данные недоступны.  С помощью объекта `CEvent` для уведомления копия поток, когда новые данные доступны, поток может выполнить свою задачу как можно скорее.  
  
 Объекты `CEvent` имеют 2 типа: ручной, так и автоматический.  
  
 Авто автоматически возвращает объект `CEvent` в сигнальное состояние \(\), не относящихся к отсутствующему после того как минимум один поток будет освобожден.  По умолчанию объект `CEvent` автоматическое если не передавая `TRUE` для параметра `bManualReset` во время разработки.  
  
 Объект `CEvent` руководства остается в состоянии установленного [SetEvent](../Topic/CEvent::SetEvent.md) или [ResetEvent](../Topic/CEvent::ResetEvent.md) до тех пор, пока другая функция не называется.  Чтобы создать объект `CEvent`, передайте `TRUE` для параметра `bManualReset` во время разработки.  
  
 Чтобы использовать объект `CEvent`, создайте объект `CEvent` при необходимости.  Укажите имя события необходимо дождаться on, а также укажите, что приложение должно иметь его.  Затем можно получить доступ событие, когда конструктор завершает работу.  Вызов [SetEvent](../Topic/CEvent::SetEvent.md) к входу \(сделайте доступно\) объект события, а затем вызывает [Unlock](../Topic/CEvent::Unlock.md) по завершении при доступе к контролируемому ресурсу.  
  
 Альтернативный метод, чтобы использовать объекты `CEvent` добавление переменной типа `CEvent` как элемент данных, к классу нужно отслеживать.  При создании управляемого объекта, вызовите конструктор элемента данных `CEvent` и указать, следует ли событие получает сигнал, а также тип specifythe объекта события, имя события \(если оно будет использоваться через границы процессов\), а все атрибуты безопасности.  
  
 Чтобы получить доступ к ресурсу проконтролированный объектом `CEvent` таким образом, сначала создайте переменную или типа [CSingleLock](../../mfc/reference/csinglelock-class.md) или введите [CMultiLock](../../mfc/reference/cmultilock-class.md) в методе доступа данного ресурса.  Затем вызовите метод `Lock` объекта блокировки \(например, [CMultiLock::Lock](../Topic/CMultiLock::Lock.md)\).  На этом этапе в поток или получит доступ к ресурсу, ожидание ресурсов для освобождения и доступа, увеличения или ожидает ресурс для освобождения, время ожидания и fail получить доступ к ресурсу.  В любом случае ресурс был доступ потокобезопасным способом.  Для освобождения ресурса, вызов `SetEvent` для обозначения объект события, а затем использовать метод `Unlock` объекта блокировки \(например, [CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)\) или препятствовал блокировки возразить падение из области.  
  
 Дополнительные сведения о том, как использовать объекты `CEvent` см. в разделе [Многопоточность. Использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Пример  
 [!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/CPP/cevent-class_1.cpp)]  
  
 [!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/CPP/cevent-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## Требования  
 **Header:**  afxmt.h  
  
## См. также  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)