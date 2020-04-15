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
ms.openlocfilehash: 9730e7baf9589c4b05a60703c619aae2e941bdec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372761"
---
# <a name="sdi-and-mdi"></a>SDI и MDI

MFC упрощает работу как с однодокументным интерфейсом (SDI), так и с многодокументными интерфейсами (MDI).

Приложения SDI позволяют одновременно открывать окно кадра документа. Приложения MDI позволяют открывать несколько окон кадра документов в одном экземпляре приложения. Приложение MDI имеет окно, в котором могут быть открыты несколько детских окон MDI, которые сами являются окнами кадра, каждый из которых содержит отдельный документ. В некоторых приложениях окна ребенка могут быть разных типов, таких как окна диаграмм и окна электронных таблиц. В этом случае панель меню может меняться по мере активации детских окон MDI различных типов.

> [!NOTE]
> В соответствии с Windows 95 и позже, приложения обычно SDI, потому что операционная система приняла "документ-центре" зрения.

Для получения дополнительной [информации см.](../mfc/documents-views-and-the-framework.md)

## <a name="see-also"></a>См. также раздел

[Использование классов для создания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
