---
title: С помощью IDispEventSimpleImpl (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventSimpleImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cdef5012288b7f5f17040f73dfac5ec1f90d4f0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361957"
---
# <a name="using-idispeventsimpleimpl"></a>С помощью IDispEventSimpleImpl
При использовании `IDispEventSimpleImpl` для обработки событий, необходимо:  
  
-   Создайте производный класс от [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md).  
  
-   Добавьте картой приемника событий в класс.  
  
-   Определение [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) структуры, описывающий события.  
  
-   Добавить записи в карте приемник событий, используя [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) макрос.  
  
-   Реализуйте методы, что вы заинтересованы в обработке.  
  
-   Сообщить и разъединения источника события.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показано, как обрабатывать **DocumentChange** события, создаваемые в Word **приложения** объекта. Это событие определяется как метод на **ApplicationEvents** disp-интерфейса.  
  
 Приведенный пример взят из [ATLEventHandling пример](../visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 В этом примере `#import` для создания файлов обязательный заголовок из библиотеки типов в Word. Если вы хотите использовать этот пример с другими версиями Microsoft Word, необходимо указать правильный mso dll-файла. Например Office 2000 предоставляет mso9.dll и OfficeXP предоставляет mso.dll. Этот код был упрощен из stdafx.h:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]  
  
 Только сведения из библиотеки типов, фактически используемый в этом примере — это CLSID слова **приложения** объекта и идентификатор IID **ApplicationEvents** интерфейса. Эта информация используется только во время компиляции.  
  
 Следующий код отображается в Simple.h. Комментарии в указывается соответствующий код:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]  
  
 Приведенный ниже код взят из Simple.cpp.  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Обработка событий](../atl/event-handling-and-atl.md)   
 [Образец ATLEventHandling](../visual-cpp-samples.md)

