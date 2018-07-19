---
title: ATL и бесплатным упаковщик | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 015b07e5870aa6269dc76af8610d42fb469a6d33
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848354"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL и упаковщик в режиме свободного потока
Мастер простых объектов ATL атрибуты страница содержит параметр, разрешающий класса для статистической обработки свободного упаковщик (FTM).  
  
 Мастер формирует код для создания экземпляра бесплатной упаковщик `FinalConstruct` и выпуска этого экземпляра в `FinalRelease`. Макрос COM_INTERFACE_ENTRY_AGGREGATE автоматически добавляется в сопоставление COM, чтобы убедиться, что `QueryInterface` запрашивает для [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) обрабатываются свободного упаковщик.  
  
 Бесплатный упаковщик обеспечивает прямой доступ, к интерфейсам в объекте, из любого потока, в том же процессе, ускоряя вызовов между подразделениями. Этот параметр предназначен для классов, использующих обе модели потоков.  
  
 При использовании этого параметра, классы должен нести ответственность за безопасность потоков данных. Кроме того объекты, которые статистическая обработка свободного упаковщик и должны использовать указатели интерфейса получен из других объектов должны предпринять дополнительные действия, чтобы убедиться, что интерфейсы маршалируются правильно. Как правило, это подразумевает хранение указателе на интерфейс в глобальной таблицы интерфейсов (GIT) и получение указателя из GIT каждый раз, когда он используется. Библиотека ATL предоставляет класс [CComGITPtr](../atl/reference/ccomgitptr-class.md) по использованию указателя на интерфейс, хранящиеся в GIT.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [Когда следует использовать глобальной таблицы интерфейсов](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Внутрипроцессный сервер потоками](http://msdn.microsoft.com/library/windows/desktop/ms687205)

