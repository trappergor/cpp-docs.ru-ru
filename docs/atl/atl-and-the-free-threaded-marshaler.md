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
ms.openlocfilehash: b9baff9af10cd785554e849854556a9aa3bd7ca4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621849"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL и упаковщик в режиме свободного потока

Мастер простых объектов ATL атрибуты страница содержит параметр, разрешающий класса для статистической обработки свободного упаковщик (FTM).

Мастер формирует код для создания экземпляра бесплатной упаковщик `FinalConstruct` и выпуска этого экземпляра в `FinalRelease`. Макрос COM_INTERFACE_ENTRY_AGGREGATE автоматически добавляется в сопоставление COM, чтобы убедиться, что `QueryInterface` запрашивает для [IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal) обрабатываются свободного упаковщик.

Бесплатный упаковщик обеспечивает прямой доступ, к интерфейсам в объекте, из любого потока, в том же процессе, ускоряя вызовов между подразделениями. Этот параметр предназначен для классов, использующих обе модели потоков.

При использовании этого параметра, классы должен нести ответственность за безопасность потоков данных. Кроме того объекты, которые статистическая обработка свободного упаковщик и должны использовать указатели интерфейса получен из других объектов должны предпринять дополнительные действия, чтобы убедиться, что интерфейсы маршалируются правильно. Как правило, это подразумевает хранение указателе на интерфейс в глобальной таблицы интерфейсов (GIT) и получение указателя из GIT каждый раз, когда он используется. Библиотека ATL предоставляет класс [CComGITPtr](../atl/reference/ccomgitptr-class.md) по использованию указателя на интерфейс, хранящиеся в GIT.

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)<br/>
[CoCreateFreeThreadedMarshaler](/windows/desktop/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal)<br/>
[Когда следует использовать глобальной таблицы интерфейсов](/windows/desktop/com/when-to-use-the-global-interface-table)<br/>
[Внутрипроцессный сервер потоками](/windows/desktop/com/in-process-server-threading-issues)

