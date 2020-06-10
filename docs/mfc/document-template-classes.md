---
title: Классы шаблонов документов
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
ms.openlocfilehash: dffde80093f98fc1c81a6c20dfaf92b82e3b4c78
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618987"
---
# <a name="document-template-classes"></a>Классы шаблонов документов

Объекты шаблона документа координируют создание объектов документа, представления и окна фрейма при создании нового документа или представления.

[CDocTemplate](reference/cdoctemplate-class.md)<br/>
Базовый класс для шаблонов документов. Этот класс никогда не будет использоваться напрямую. Вместо этого используется один из других классов шаблонов документов, производных от этого класса.

[CMultiDocTemplate](reference/cmultidoctemplate-class.md)<br/>
Шаблон для документов в многодокументном интерфейсе (MDI). Приложения MDI могут одновременно открывать несколько документов.

[CSingleDocTemplate](reference/csingledoctemplate-class.md)<br/>
Шаблон для документов в интерфейсе одиночного документа (SDI). В приложениях SDI одновременно открыт только один документ.

## <a name="related-class"></a>Связанный класс

[ккреатеконтекст](reference/ccreatecontext-structure.md)<br/>
Структура, передаваемая шаблоном документа функциям создания окна для координации создания объектов документа, представления и окна фрейма.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
