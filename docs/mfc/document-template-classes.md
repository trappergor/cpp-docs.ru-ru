---
title: Классы шаблонов документов
ms.date: 11/04/2016
f1_keywords:
- vc.classes.document
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
ms.openlocfilehash: 2589bc8f04e791f73529af91ffb148c2c717cd08
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164993"
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
