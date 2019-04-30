---
title: SDI и MDI
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
ms.openlocfilehash: 725249e5a71e8ee097c641e5972e3cc8bb0e3e33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308541"
---
# <a name="sdi-and-mdi"></a>SDI и MDI

MFC упрощает работу с однооконным интерфейсом (SDI) и приложений многодокументного интерфейса (MDI).

Приложения SDI разрешить только одно окно фрейма открытый документ за раз. Приложения MDI разрешает несколько документов, окон фрейма, необходимо открыть на том же экземпляре приложения. MDI-приложения с периодом в какие MDI несколько дочерних окон, которые являются окна фрейма, сами, можно открыть, каждая из которых содержит отдельный документ. В некоторых приложениях в дочерние окна может быть разных типов, таких как диаграммы и таблицы окна. В этом случае в строке меню можно изменить как активируются дочерние окна MDI различных типов.

> [!NOTE]
>  В Windows 95 и более поздних версиях приложений обычно представляют собой SDI так, как операционная система была внедрена представления «документ по центру».

Дополнительные сведения см. в разделе [документы, представления и платформа](../mfc/documents-views-and-the-framework.md).

## <a name="see-also"></a>См. также

[Использование классов для создания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
