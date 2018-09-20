---
title: Классы шаблонов документов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87984bf06d8ca178d2a21ac8ff475f828690668e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406065"
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

