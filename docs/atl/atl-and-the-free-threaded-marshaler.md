---
title: "Упаковщик в режиме ATL и бесплатный | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 02b8586d7df5a521b48bfce61a097ed6ca450196
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL и упаковщик в режиме свободного потока
Мастер простых объектов ATL атрибуты страница содержит параметр, разрешающий класса для статистической обработки свободного упаковщик в режиме потока (FTM).  
  
 Мастер создает код для создания экземпляра свободного упаковщик в режиме потока в `FinalConstruct` и выпуск экземпляра в `FinalRelease`. Объект `COM_INTERFACE_ENTRY_AGGREGATE` макрос автоматически добавляется к сопоставлению COM, чтобы убедиться, что `QueryInterface` запросы для [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) обрабатываются упаковщиком свободных потоков.  
  
 Упаковщик свободных потоков позволяет прямой доступ интерфейсы объекта из любого потока, в том же процессе ускоряет вызовы между подразделениями. Этот параметр предназначен для классов, использующих обе модели потоков.  
  
 При использовании этого параметра, классы ложится ответственность за безопасность потоков данных. Кроме того объекты, которые статистическая обработка свободного упаковщик в режиме потока и необходимо использовать указатели на интерфейс, полученный от других объектов должны предпринять дополнительные действия, чтобы убедиться, что интерфейсы маршалируются правильно. Как правило, это подразумевает хранение указателей интерфейса в глобальной таблицы интерфейсов (GIT) и получение указателя из GIT при каждом использовании. Библиотека ATL предоставляет класс [CComGITPtr](../atl/reference/ccomgitptr-class.md) помогут вам использовать указатели на интерфейс, хранящиеся в GIT.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [Когда следует использовать глобальной таблицы интерфейсов](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Процесс сервера потоками](http://msdn.microsoft.com/library/windows/desktop/ms687205)

