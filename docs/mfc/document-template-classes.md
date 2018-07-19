---
title: Классы шаблонов документов | Документы Microsoft
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
ms.openlocfilehash: d9958484633dd736426fc91321d0964abf0ad7e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343547"
---
# <a name="document-template-classes"></a>Классы шаблонов документов
Шаблон документа объекты координации создания документов, представления и объекты окон фрейма, при создании нового документа или создать представление.  
  
 [CDocTemplate](../mfc/reference/cdoctemplate-class.md)  
 Базовый класс для шаблонов документов. Никогда не будет использовать этот класс непосредственно. Вместо этого используйте один из других классов шаблонов документов, производный от этого класса.  
  
 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)  
 Шаблон для документов в многодокументный интерфейс (MDI). MDI-приложения может иметь одновременно открыть несколько документов.  
  
 [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)  
 Шаблон для документов в однооконный интерфейс (SDI). SDI-приложения имеют только один документ открыть одновременно.  
  
## <a name="related-class"></a>Связанный класс  
 [CCreateContext](../mfc/reference/ccreatecontext-structure.md)  
 Передает структуру шаблона документа в функции создания окна для координации создание объектов документов, представления и окна фрейма.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

