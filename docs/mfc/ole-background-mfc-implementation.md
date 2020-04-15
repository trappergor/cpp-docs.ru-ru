---
title: Поддержка OLE. Реализация MFC
ms.date: 11/04/2016
f1_keywords:
- IMarshall
- IMoniker
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
ms.openlocfilehash: 25c98c3683a8656bb5188f22d0464d25a4901f49
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364531"
---
# <a name="ole-background-mfc-implementation"></a>Поддержка OLE. Реализация MFC

Из-за размера и сложности необработанного API OLE, вызов его непосредственно для написания приложений OLE может занять очень много времени. Цель юриспроекта библиотеки Фонда Майкрософт – сократить объем работы, которую необходимо сделать, чтобы написать полнофункциональные приложения, способные на OLE.

В этой статье разъясняются части API OLE, которые не были реализованы внутри MFC. Обсуждение также объясняет, как то, что реализовано карты в разделе OLE Windows SDK.

## <a name="portions-of-ole-not-implemented-by-the-class-library"></a><a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a>Части OLE не реализованы библиотекой класса

Несколько интерфейсов и функций OLE напрямую не предоставляются MFC. Если вы хотите использовать эти функции, вы можете вызвать API OLE напрямую.

Интерфейс IMoniker `IMoniker` Интерфейс реализован библиотекой класса (например, `COleServerItem` классом), но ранее не подвергался воздействию программиста. Для получения дополнительной информации об этом интерфейсе см. Тем не менее, см. также класс [CMonikerFile](../mfc/reference/cmonikerfile-class.md) и [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).

Интерфейс IUnknown и IMarshal Интерфейс `IUnknown` реализован библиотекой класса, но не подвергается воздействию программиста. Интерфейс `IMarshal` не реализуется библиотекой класса, а используется внутри. Серверы автоматизации, построенные с помощью библиотеки классов, уже имеют встроенные возможности маршалинга.

Файлы составных файлов Docfiles (Compound Files) частично поддерживаются библиотекой классов. Ни одна из функций, которые непосредственно манипулировать составных файлов за пределами создания не поддерживаются. MFC использует `COleFileStream` класс для поддержки манипуляций потоками со стандартными функциями файлов. Для получения дополнительной информации, [см.](../mfc/containers-compound-files.md)

Серверы в процессе обработки и обработчики объектов In-process и обработчики объектов позволяют осуществлять данные визуального редактирования или объекты полной модели компонентов (COM) в библиотеке динамических ссылок (DLL). Для этого вы можете реализовать свой DLL, позвонив на API OLE напрямую. Однако, если вы пишете сервер автоматизации и ваш сервер не имеет пользовательского интерфейса, вы можете использовать AppWizard, чтобы сделать ваш сервер в процессе процесса и поместить его полностью в DLL. Для получения дополнительной информации [Automation Servers](../mfc/automation-servers.md)по этим темам см.

> [!TIP]
> Самый простой способ реализации сервера автоматизации — поместить его в DLL. MFC поддерживает этот подход.

Для получения дополнительной информации о том, как классы Microsoft [38](../mfc/tn038-mfc-ole-iunknown-implementation.md)Foundation [39](../mfc/tn039-mfc-ole-automation-implementation.md)OLE внедряют интерфейсы OLE, см. [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)

## <a name="see-also"></a>См. также раздел

[Поддержка OLE](../mfc/ole-background.md)<br/>
[Поддержка OLE. Стратегии реализации](../mfc/ole-background-implementation-strategies.md)
