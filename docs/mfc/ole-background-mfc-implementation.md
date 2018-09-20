---
title: 'Поддержка OLE: Реализация MFC | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IMarshall
- IMoniker
dev_langs:
- C++
helpviewer_keywords:
- MFC libraries, implementing
- OLE MFC library implementation
- OLE IMarshal interface
- IMoniker interface, MFC
- IMarshall class [MFC]
- OLE, compound files
- OLE IMoniker interface
- OLE IUnknown
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d6fdd0fa05ec21151a28c516adcb224f5e9b0ec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409835"
---
# <a name="ole-background-mfc-implementation"></a>Поддержка OLE. Реализация MFC

Из-за размера и сложности OLE интерфейсе API вызов его напрямую для написания приложений OLE может занять очень много времени. Реализация библиотеки MFC OLE призван уменьшить объем работы, что необходимо сделать для написания приложений полнофункциональный, поддержкой OLE.

В этой статье объясняется части OLE API, которые не были реализованы в MFC. Обсуждение также объясняется, как новые реализуется сопоставляет к разделу OLE пакета Windows SDK.

##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> Некоторые части OLE, не реализованы в библиотеке классов

Несколько интерфейсов и особенностей OLE не предоставляются непосредственно в MFC. Если вы хотите использовать эти функции, можно напрямую вызвать OLE API.

IMoniker-интерфейс `IMoniker` интерфейс реализуется библиотекой классов (например, `COleServerItem` класс), но ранее не была доступна для программиста. Дополнительные сведения об этом интерфейсе см. в разделе OLE моникер реализаций в разделе OLE пакета Windows SDK. Тем не менее, см. также класс [CMonikerFile](../mfc/reference/cmonikerfile-class.md) и [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).

IUnknown и интерфейсы IMarshal `IUnknown` интерфейс реализуется библиотекой классов, но остается невидимым для программиста. `IMarshal` Интерфейса не реализован в библиотеке классов, но для внутреннего использования. Серверы автоматизации, созданные с помощью библиотеки классов, уже имеют маршалинг встроенных возможностей.

Составные файлы DOCFILES (составные файлы), частично поддерживаются библиотекой классов. Ни одна из функций, которые непосредственно управляют составные файлы за пределами создания поддерживаются. MFC использует класс `COleFileStream` для поддержки обработки потоков с функциями стандартный файл. Дополнительные сведения см. в статье [контейнеры: составные файлы](../mfc/containers-compound-files.md).

Внутрипроцессные серверы и дескрипторами объектов внутренних серверов и дескрипторами объектов позволяет реализовать визуального редактирования данных или полными объектами компонента объекта модели (COM) в библиотеке динамической компоновки (DLL). Чтобы сделать это, можно реализовать путем прямого вызова OLE API библиотеки DLL. Тем не менее если вы создаете сервер автоматизации и серверу у него отсутствует интерфейс пользователя, можно использовать мастером приложений, сделать ваш сервер в процессе и помещать его полностью в библиотеку DLL. Дополнительные сведения об этих темах см. в разделе [серверы автоматизации](../mfc/automation-servers.md).

> [!TIP]
>  Для реализации сервера автоматизации проще всего поместить его в библиотеке DLL. MFC поддерживает такой подход.

Дополнительные сведения о том, как классы Microsoft Foundation OLE реализовывать интерфейсы OLE, см. в разделе Технические примечания MFC [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), и [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).

## <a name="see-also"></a>См. также

[Поддержка OLE](../mfc/ole-background.md)<br/>
[Поддержка OLE. Стратегии реализации](../mfc/ole-background-implementation-strategies.md)

