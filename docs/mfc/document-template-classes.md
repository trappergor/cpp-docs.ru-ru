---
title: Классы шаблонов документов
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
ms.openlocfilehash: 82b9ce4c242df7c85ada0722b2c1e993a0cf3f81
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446910"
---
# <a name="document-template-classes"></a>Классы шаблонов документов

Объекты шаблона документа координируют создание объектов документа, представления и окна фрейма при создании нового документа или представления.

[CDocTemplate](../mfc/reference/cdoctemplate-class.md)<br/>
Базовый класс для шаблонов документов. Этот класс никогда не будет использоваться напрямую. Вместо этого используется один из других классов шаблонов документов, производных от этого класса.

[кмултидоктемплате](../mfc/reference/cmultidoctemplate-class.md)<br/>
Шаблон для документов в многодокументном интерфейсе (MDI). Приложения MDI могут одновременно открывать несколько документов.

[ксингледоктемплате](../mfc/reference/csingledoctemplate-class.md)<br/>
Шаблон для документов в интерфейсе одиночного документа (SDI). В приложениях SDI одновременно открыт только один документ.

## <a name="related-class"></a>Связанный класс

[ккреатеконтекст](../mfc/reference/ccreatecontext-structure.md)<br/>
Структура, передаваемая шаблоном документа функциям создания окна для координации создания объектов документа, представления и окна фрейма.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../mfc/class-library-overview.md)
