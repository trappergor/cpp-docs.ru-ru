---
title: "Классы шаблонов документов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbaccd12daf156d4a15f5cd18c31b5b230fe86db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

