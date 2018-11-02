---
title: Классы шаблонов документов
ms.date: 11/04/2016
f1_keywords:
- vc.classes.document
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
ms.openlocfilehash: b15263005f8bd6a8fdc9f9f29ea268fe8a6b95a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448078"
---
# <a name="document-template-classes"></a>Классы шаблонов документов

Объекты шаблонов документов координации создания документов, представления и объекты окон фрейма при создании нового документа или создании представления.

[CDocTemplate](../mfc/reference/cdoctemplate-class.md)<br/>
Базовый класс для шаблонов документов. Никогда не будет использовать этот класс напрямую. Вместо этого используйте один из других классов шаблонов документов, производный от этого класса.

[CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)<br/>
Шаблон для документов в многодокументного интерфейса (MDI). MDI-приложения может иметь одновременно открыто несколько документов.

[CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)<br/>
Шаблон для документов в интерфейс одного документа (SDI). SDI-приложения имеют только один документ за раз откройте.

## <a name="related-class"></a>Связанный класс

[CCreateContext](../mfc/reference/ccreatecontext-structure.md)<br/>
Структуры, передаваемые в шаблоне документа функции создания окна для координации создания объектов документов, представления и окна фрейма.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

