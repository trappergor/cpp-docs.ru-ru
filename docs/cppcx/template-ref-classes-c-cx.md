---
title: Классы ссылки шаблонов (C + +/ CX) | Документы Microsoft
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1d637eeee0ff087a0c8f07d7929f6d4dcf13247
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088054"
---
# <a name="template-ref-classes-ccx"></a>Классы ссылки шаблонов (C++/CX)
Шаблоны C++ не публикуются в метаданных и поэтому не могут иметь быть открытыми или защищенными в программе. Конечно внутри программы можно использовать стандартные шаблоны C++. Кроме того, можно определить закрытый класс ссылки в качестве шаблона и объявить явно специализированный класс ссылки шаблона в качестве закрытого члена открытого класса ссылки.  
  
## <a name="authoring-ref-class-templates"></a>Создание шаблонов классов ссылок  
 В следующем примере показано, как объявить закрытый класс ссылки в виде шаблона, как объявить стандартный шаблон C++ и как объявить такие класс и шаблон в качестве членов открытого класса ссылки. Обратите внимание, что стандартный шаблон C++ может специализированным, тип среды выполнения Windows, в данном случае Platform::String ^.  
  
 [!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]  
  
## <a name="see-also"></a>См. также  
 [Система типов (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)