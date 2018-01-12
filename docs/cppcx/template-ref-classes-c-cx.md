---
title: "Классы ссылки шаблонов (C + +/ CX) | Документы Microsoft"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b8bb720ef9275f9023cf15986f011573f4c510b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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