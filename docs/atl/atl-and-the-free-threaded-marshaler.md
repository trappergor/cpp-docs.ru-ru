---
title: ATL и упаковщик в режиме свободного потока
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
ms.openlocfilehash: 94e4961c69e9441d160d72d9b72afcee3677e25f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491913"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL и упаковщик в режиме свободного потока

Страница атрибутов мастера простых объектов ATL предоставляет параметр, позволяющий классу объединять бесплатный потоковый маршалеру (FTM).

Мастер создает код для создания экземпляра свободного потокового маршалером в `FinalConstruct` и выпуска этого экземпляра в. `FinalRelease` Макрос COM_INTERFACE_ENTRY_AGGREGATE автоматически добавляется в карту com, чтобы обеспечить `QueryInterface` обработку запросов для [IMarshal](/windows/win32/api/objidlbase/nn-objidlbase-imarshal) с помощью свободного потокового модуля.

Свободный потоковый маршалинг обеспечивает прямой доступ к интерфейсам объекта из любого потока в том же процессе, ускоряя вызовы между апартаментами. Этот параметр предназначен для классов, использующих модель потоков.

При использовании этого параметра классы должны принимать ответственность за потокобезопасность данных. Кроме того, объекты, которые выполняют статистическую обработку свободного потокового маршалером и должны использовать указатели интерфейса, полученные из других объектов, должны предпринимать дополнительные действия, чтобы обеспечить правильную упаковку интерфейсов. Обычно это подразумевает хранение указателей интерфейса в глобальной таблице интерфейса (GIT) и получение указателя из GIT при каждом использовании. ATL предоставляет класс [ккомгитптр](../atl/reference/ccomgitptr-class.md) , помогающий использовать указатели интерфейса, хранящиеся в Git.

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)<br/>
[кокреатефрисреадедмаршалер](/windows/win32/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[IMarshal](/windows/win32/api/objidlbase/nn-objidlbase-imarshal)<br/>
[Когда следует использовать глобальную таблицу интерфейса](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Проблемы потоковой обработки в процессе сервера](/windows/win32/com/in-process-server-threading-issues)
