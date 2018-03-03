---
title: "Общие изменения в языке (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 79a70768-225c-4ae2-84d1-178b20a9b042
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 87ff7f55b67c4e8a84d15099432962ee0939d13a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="general-language-changes-ccli"></a>Общие изменения в языке (C++/CLI)
Число функций языка среды CLR, изменилось с управляемых расширений для C++ к Visual C++.  
  
 Изменения, описанные в этом разделе, представляют собой своего рода набор статей языка. Он включает изменение в обработке строковых литералов, изменение в разрешении перегрузки между многоточие и `Param` атрибут изменение `typeof` для `typeid`, изменения в вызывающем списки инициализации и введение новой нотации, `safe_cast`.  
  
 [Строковый литерал](../dotnet/string-literal.md)  
 Описывает, как изменилась обработка строковых литералов.  
  
 [Массив Param и многоточие](../dotnet/param-array-and-ellipsis.md)  
 Рассматриваются как `ParamArray` теперь получает приоритет над кнопку с многоточием (`...`) при разрешении вызовов функций с переменным числом аргументов.  
  
 [Переход typeof в T::typeid](../dotnet/typeof-goes-to-t-typeid.md)  
 Рассматриваются как `typeof` причинах замещения оператора `typeid`.  
  
 [Списки инициализатора](../dotnet/initializer-lists.md)  
 Рассматриваются изменения в порядке вызовов списков инициализаторов.  
  
 [Нотация приведения типов и знакомство с safe_cast<>](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)  
 Описание новых изменениях в нотации приведений и в частности `safe_cast`.  
  
## <a name="see-also"></a>См. также  
 [Основы миграции C++/CLI](../dotnet/cpp-cli-migration-primer.md)