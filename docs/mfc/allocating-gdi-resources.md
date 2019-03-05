---
title: Выделение ресурсов GDI
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
ms.openlocfilehash: 5f5f6c6585217393a6008fafa875a83e67ab8016
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57305007"
---
# <a name="allocating-gdi-resources"></a>Выделение ресурсов GDI

В этой статье объясняется, как выделять и освобождать объекты интерфейса графических устройств (GDI) Windows, необходимые для печати.

> [!NOTE]
>  Дополнительные сведения см. в документации по GDI + SDK на: [ https://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp ](https://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).

Предположим, что вам требуется использовать определенные шрифты, перья или другие объекты GDI для печати, но не для отображения на экране. Из-за необходимого им объема памяти неэффективно выделить эти объекты при запуске приложения. Если приложение не печатает документ, эта память может потребоваться для других целей. Лучше выделить их, когда печать начинается, и затем удалите их.

Чтобы выделить эти объекты GDI, переопределите [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) функция-член. Эта функция идеально подходит для этой цели по двум причинам: платформа вызывает эту функцию один раз в начале каждого задания печати и, в отличие от [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting), эта функция имеет доступ к [CDC](../mfc/reference/cdc-class.md) Объект, представляющий драйвер принтера. Можно сохранить эти объекты для использования во время выполнения задания печати, определение переменных-членов в классе представления, которые указывают на объекты GDI (например, `CFont *` члены и т. д.).

Чтобы использовать созданные объекты GDI, выберите их в контекст устройства принтера в [OnPrint](../mfc/reference/cview-class.md#onprint) функция-член. Если требуются различные объекты GDI для разных страниц документа, можно изучить `m_nCurPage` членом [CPrintInfo](../mfc/reference/cprintinfo-structure.md) структурировать и выбрать объект GDI соответствующим образом. Если вам требуется объект GDI для нескольких последовательных страниц, в Windows необходимо выбирать его в контексте устройства при каждом вызове `OnPrint`.

Чтобы освободить эти объекты GDI, переопределите [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) функция-член. Платформа вызывает эту функцию в конце каждого задания печати, что дает вам возможность освободить объекты GDI для печати перед возвратом приложения к другим задачам.

## <a name="see-also"></a>См. также

[Печать](../mfc/printing.md)<br/>
[Печать по умолчанию](../mfc/how-default-printing-is-done.md)
