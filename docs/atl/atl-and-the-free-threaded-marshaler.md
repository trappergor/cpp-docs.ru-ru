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
ms.openlocfilehash: e5746fb3a4e704d866ce6e929de832d783e7afc8
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757046"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL и упаковщик в режиме свободного потока

Мастер простых объектов ATL атрибуты страница содержит параметр, разрешающий класса для статистической обработки свободного упаковщик (FTM).

Мастер формирует код для создания экземпляра бесплатной упаковщик `FinalConstruct` и выпуска этого экземпляра в `FinalRelease`. Макрос COM_INTERFACE_ENTRY_AGGREGATE автоматически добавляется в сопоставление COM, чтобы убедиться, что `QueryInterface` запрашивает для [IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal) обрабатываются свободного упаковщик.

Бесплатный упаковщик обеспечивает прямой доступ, к интерфейсам в объекте, из любого потока, в том же процессе, ускоряя вызовов между подразделениями. Этот параметр предназначен для классов, использующих обе модели потоков.

При использовании этого параметра, классы должен нести ответственность за безопасность потоков данных. Кроме того объекты, которые статистическая обработка свободного упаковщик и должны использовать указатели интерфейса получен из других объектов должны предпринять дополнительные действия, чтобы убедиться, что интерфейсы маршалируются правильно. Как правило, это подразумевает хранение указателе на интерфейс в глобальной таблицы интерфейсов (GIT) и получение указателя из GIT каждый раз, когда он используется. Библиотека ATL предоставляет класс [CComGITPtr](../atl/reference/ccomgitptr-class.md) по использованию указателя на интерфейс, хранящиеся в GIT.

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)   
[CoCreateFreeThreadedMarshaler](/windows/desktop/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)   
[IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal)   
[Когда следует использовать глобальной таблицы интерфейсов](/windows/desktop/com/when-to-use-the-global-interface-table)   
[Внутрипроцессный сервер потоками](/windows/desktop/com/in-process-server-threading-issues)

