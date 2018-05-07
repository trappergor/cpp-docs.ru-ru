---
title: Указание потоковой модели для проекта (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f807aa82a62fb703430ace5bc6be516e08ca9dc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>Указание потоковой модели для проекта (ATL)
Чтобы указать, что потоковая модель проекта ATL доступны следующие макросы:  
  
|Макрос|Рекомендации по использованию|  
|-----------|--------------------------|  
|_ATL_SINGLE_THREADED|Определите, если все объекты используют один потоковую модель.|  
|_ATL_APARTMENT_THREADED|Если один или несколько объектов использовать потоковое определите.|  
|_ATL_FREE_THREADED|Определите, если один или несколько объектов используйте свободные или нейтральной работа с потоками. Существующий код может содержать ссылки на эквивалентное макрос [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded).|  
  
 Если для проекта эти макросы не определено, _ATL_FREE_THREADED будет действовать.  
  
 Макросы влияют на производительность во время выполнения следующим образом:  
  
-   Указание макрос, который соответствует объектам в проекте может повысить производительность во время выполнения.  
  
-   Указав более высокий уровень макрос, например, при указании _ATL_APARTMENT_THREADED при соблюдении всех объектов одного потоков, немного снизится производительность во время выполнения.  
  
-   Указания более низкого уровня макрос, например, при указании _ATL_SINGLE_THREADED, когда один или несколько объектов необходимо использовать потоковое или свободной потоковой модели, может вызвать сбой во время выполнения приложения.  
  
 В разделе [параметры, мастер простых объектов ATL](../atl/reference/options-atl-simple-object-wizard.md) моделей для объекта ATL описание работы с потоками.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)

