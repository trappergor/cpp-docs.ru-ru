---
title: Необходимо ли создавать новые классы как производные от CObject? | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51904ac06ae6c2db5586f8dc405f85145c5b1f30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343064"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Необходимо ли создавать новые классы как производные от CObject?
Нет, не.  
  
 Производный класс [CObject](../mfc/reference/cobject-class.md) при необходимости помещениях, он предоставляет, например сериализации или динамических creatability. Множество классов данных необходимо сериализовать в файлы, поэтому часто рекомендуется наследовать их из `CObject`. Для примера класса, производного от `CObject`, в разделе [пример Scribble](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>См. также  
 [Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)
