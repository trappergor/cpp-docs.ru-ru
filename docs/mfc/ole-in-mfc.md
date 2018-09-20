---
title: OLE в MFC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e43484e5f30191c604f43a2280a8deab6eddd93c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434951"
---
# <a name="ole-in-mfc"></a>OLE в MFC

В этой статье рассматривается основ программирования OLE, с помощью MFC. MFC предоставляет самый простой способ создавать программы, использующие OLE:

- Для использования OLE визуального редактирования (Активация на месте).

- Для работы в качестве OLE-контейнеры или серверов.

- Для реализации функциональности перетаскивания и вставки.

- Для работы с данными даты и времени.

- Для управления данные о состоянии для MFC модулей, включая экспортировать точки входа функции DLL точки входа интерфейса OLE/COM и точки входа процедуры окна.

Можно также использовать [автоматизации](../mfc/automation.md).

> [!NOTE]
>  Термин обозначает OLE перетаскивание технологиями, связанными с связь и внедрение, включая контейнеры OLE, серверов OLE, элементы OLE, активация на месте (или Визуальное редактирование), средства отслеживания и слияние меню. Термин Active применяется к модели объектов компонента (COM) и основанные на COM объекты такие как элементы управления ActiveX. OLE-автоматизации, теперь называется автоматизации.

## <a name="in-this-section"></a>В этом разделе

[Поддержка OLE](../mfc/ole-background.md)<br/>
Описание OLE и содержатся общие сведения о том, как он работает.

[Активация](../mfc/activation-cpp.md)<br/>
Описывает роль активации в редактирования элементов OLE.

[Контейнеры](../mfc/containers.md)<br/>
Ссылки на использование контейнеров в OLE.

[Объекты и источники данных](../mfc/data-objects-and-data-sources-ole.md)<br/>
Ссылки на статьи, описывающие использование `COleDataObject` и `COleDataSource` классы.

[Перетаскивание](../mfc/drag-and-drop-ole.md)<br/>
Рассматривает использование, копирование и вставка с OLE.

[Меню и ресурсы OLE](../mfc/menus-and-resources-ole.md)<br/>
Описание меню и ресурсы в приложениях MFC OLE документа.

[Регистрация](../mfc/registration.md)<br/>
Описание установки сервера и инициализации.

[Серверы](../mfc/servers.md)<br/>
В этой статье описывается создание OLE элементов (или компоненты) для использования приложением-контейнером.

[Средства отслеживания](../mfc/trackers.md)<br/>
Предоставляет сведения о `CRectTracker` класс, который предоставляет графический интерфейс, чтобы пользователи могли взаимодействовать с элементами клиента OLE.

## <a name="related-sections"></a>Связанные разделы

[Точки подключения](../mfc/connection-points.md)<br/>
Объясняет, как будут реализованы точки соединения (прежнее название OLE точки подключения) с использованием классов MFC `CCmdTarget` и `CConnectionPoint`.

[Контейнера и сервера COM-компонентов](../mfc/containers-advanced-features.md)<br/>
Описывает действия, необходимые для включения необязательно расширенных возможностей в существующие приложения-контейнеры.

[Модель COM](/windows/desktop/com/the-component-object-model)<br/>
Описывает использование OLE без использования MFC.

## <a name="see-also"></a>См. также

[Основные понятия](../mfc/mfc-concepts.md)

